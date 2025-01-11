# Hierarchical-Bayesian-Models-for-U.S.-COVID-19-Spread

'''

install.packages(mgcv)
install.packages("ggpubr")
install.packages(ggplot2)(ggpubr)
install.packages(egg)
install.packages(moonBook)
install.packages(ztable)
install.packages(ggGAM)
install.packages("MASS")  # Boston DataSet
data("Boston")  
head(Boston)    

require(mgcv)
require(ggplot2)
require(ggpubr)
require(egg)
require(moonBook)
require(ztable)
require(ggGAM)

'''

'''
gam_model <- gam(medv ~ s(lstat) + s(rm) + s(dis) + s(nox) + s(crim),
data = Boston,
method = "REML")
summary(gam_model)
par(mfrow = c(2, 3))  # Arrange plots in a grid
plot(gam_model, se = TRUE, shade = TRUE)

'''



![스크린샷 2025-01-11 06-07-26](https://github.com/user-attachments/assets/d9f3f7d3-a973-4325-9124-71e824b8168e)

'''
cat("Adjusted R-squared: ", summary(gam_model)$r.sq, "\n")
'''

![스크린샷 2025-01-11 06-07-42](https://github.com/user-attachments/assets/438f26d0-a72e-47fa-93e8-ac8ee16b01c5)

![스크린샷 2025-01-11 06-07-51](https://github.com/user-attachments/assets/05d0a1c1-3c75-4c2f-bacb-520043c34994)

![스크린샷 2025-01-11 06-07-57](https://github.com/user-attachments/assets/9bba9409-4ac9-4d09-a8fb-fcd3a2ede352)

![스크린샷 2025-01-11 06-08-10](https://github.com/user-attachments/assets/5c44dfa1-99aa-4b22-aa0d-401951c16438)

![스크린샷 2025-01-11 06-08-29](https://github.com/user-attachments/assets/5fee88c5-cec3-4674-be62-2297bcf0f512)

![스크린샷 2025-01-11 06-08-02](https://github.com/user-attachments/assets/45f9c9db-5dbd-4c7d-8bdf-befa22a2b6ec)

![스크린샷 2025-01-11 06-08-14](https://github.com/user-attachments/assets/2602bbf6-c213-44ce-a4b7-bdcd12860da8)

![스크린샷 2025-01-11 06-10-34](https://github.com/user-attachments/assets/b1b5e933-4761-4c65-a27d-11151f6a8040)
