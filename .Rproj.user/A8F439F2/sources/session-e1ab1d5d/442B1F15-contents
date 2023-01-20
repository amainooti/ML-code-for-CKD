
# Load the necessary libraries
library(rpart)
library(rpart.plot)

# Import and prepare the data
data <- read.csv("C:\\Users\\OTI\\Downloads\\CKD_Metals_in_Urine.csv")

# Split the data into training and testing sets
set.seed(123)
split <- sample.split(data$chronic_kidney_disease, SplitRatio = 0.7)
train <- subset(data, split == TRUE)
test <- subset(data, split == FALSE)

# Build the decision tree model
model <- rpart(chronic_kidney_disease ~ age + sex + blood_pressure + diabetes + glomerular_filtration_rate, data = train, method = "class")

# Plot the decision tree
rpart.plot(model, type = 4, extra = 1)

# Make predictions on the test set
predictions <- predict(model, newdata = test, type = "class")

# Evaluate the model's performance
library(caret)
confusionMatrix(predictions, test$chronic_kidney_disease)
