# Hierarchical-Bayesian-Models-for-U.S.-COVID-19-Spread



```
data_new <- data_table

model_updated <- lmer(median ~ lower + upper + (1 | state_abb), data = data_new,
                      control = lmerControl(optCtrl = list(maxfun = 10000)))

summary(model_updated)

predictions <- predict(model_updated, newdata = data_table, re.form = ~0)

data_table$predicted_median <- predictions

library(ggplot2)

ggplot(data_table, aes(x = median, y = predicted_median)) +
  geom_point(aes(color = state_abb)) +
  geom_abline(slope = 1, intercept = 0, linetype = "dashed", color = "red") +  
  labs(title = "Actual vs Predicted Median",
       x = "Actual Median",
       y = "Predicted Median") +
  theme_minimal()




```

![스크린샷 2025-01-11 06-07-42](https://github.com/user-attachments/assets/438f26d0-a72e-47fa-93e8-ac8ee16b01c5)

```
random_effects <- ranef(model)$state_abb
random_effects_df <- data.frame(state_abb = rownames(random_effects), random_effect = random_effects[, 1])

ggplot(random_effects_df, aes(x = state_abb, y = random_effect)) +
  geom_bar(stat = "identity") +
  labs(title = "Random Effects by State", x = "State", y = "Random Effect")
```

![스크린샷 2025-01-11 06-07-51](https://github.com/user-attachments/assets/05d0a1c1-3c75-4c2f-bacb-520043c34994)

![스크린샷 2025-01-11 06-07-57](https://github.com/user-attachments/assets/9bba9409-4ac9-4d09-a8fb-fcd3a2ede352)

![스크린샷 2025-01-11 06-08-10](https://github.com/user-attachments/assets/5c44dfa1-99aa-4b22-aa0d-401951c16438)

![스크린샷 2025-01-11 06-08-29](https://github.com/user-attachments/assets/5fee88c5-cec3-4674-be62-2297bcf0f512)

![스크린샷 2025-01-11 06-08-02](https://github.com/user-attachments/assets/45f9c9db-5dbd-4c7d-8bdf-befa22a2b6ec)

![스크린샷 2025-01-11 06-08-14](https://github.com/user-attachments/assets/2602bbf6-c213-44ce-a4b7-bdcd12860da8)

![스크린샷 2025-01-11 06-10-34](https://github.com/user-attachments/assets/b1b5e933-4761-4c65-a27d-11151f6a8040)
