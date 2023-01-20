# Load the necessary libraries
library(class)

# Import and prepare the data
data <- read.csv("C:\\Users\\OTI\\Downloads\\CKD_Metals_in_Urine.csv")

# Split the data into training and testing sets
set.seed(123)
split <- sample.split(data$chronic_kidney_disease, SplitRatio = 0.7)
train <- subset(data, split == TRUE)
test <- subset(data, split == FALSE)

# Build the KNN model
model <- knn(train[, -ncol(train)], test[, -ncol(test)], train$chronic_kidney_disease, k = 5)

# Make predictions on the test set
predictions <- model

# Evaluate the model's performance
library(caret)
confusionMatrix(predictions, test$chronic_kidney_disease)
