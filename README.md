# Developing a Neural Network Regression Model

## AIM

To develop a neural network regression model for the given dataset.

## THEORY

The objective of this project is to develop a Neural Network Regression Model that can accurately predict a target variable based on input features. The model will leverage deep learning techniques to learn intricate patterns from the dataset and provide reliable predictions.

## Neural Network Model

![Screenshot 2025-03-03 112637](https://github.com/user-attachments/assets/b02f5aef-bf22-456f-82b7-aaa54124cf66)

## DESIGN STEPS

### STEP 1:

Loading the dataset

### STEP 2:

Split the dataset into training and testing

### STEP 3:

Create MinMaxScalar objects ,fit the model and transform the data.

### STEP 4:

Build the Neural Network Model and compile the model.

### STEP 5:

Train the model with the training data.

### STEP 6:

Plot the performance plot

### STEP 7:

Evaluate the model with the testing data.

## PROGRAM
### Name:HARISHA S
### Register Number:212223040063
```python
class NeuralNet(nn.Module):
  def __init__(self):
        super().__init__()
        self.fc1=nn.Linear(1,10)
        self.fc2=nn.Linear(10,12)
        self.fc3=nn.Linear(12,1)
        self.relu=nn.ReLU()
        self.history={'loss': []}

  def forward(self, x):
    x=self.relu(self.fc1(x))
    x=self.relu(self.fc2(x))
    x=self.fc3(x)
    return x




# Initialize the Model, Loss Function, and Optimizer
ai_brain=NeuralNet()
criterion=nn.MSELoss()
optimizer=optim.RMSprop(ai_brain.parameters(),lr=0.001)


def train_model(ai_brain, X_train, y_train, criterion, optimizer, epochs=2000):
  for epoch in range(epochs):
        optimizer.zero_grad()
        loss = criterion(ai_brain(X_train), y_train)
        loss.backward()
        optimizer.step()

        ai_brain.history['loss'].append(loss.item())
        if epoch % 200 == 0:
            print(f'Epoch [{epoch}/{epochs}], Loss: {loss.item():.6f}')


```
## Dataset Information

![image](https://github.com/user-attachments/assets/48709095-b67f-414a-9316-c03e4bb4383f)


## OUTPUT

### Training Loss Vs Iteration Plot

![download](https://github.com/user-attachments/assets/7ece4ada-81ce-40ee-bd6b-3135284f38b2)

### New Sample Data Prediction

![image](https://github.com/user-attachments/assets/47e02c39-167f-4722-be69-b87a11f30f91)


## RESULT
The neural network regression model was successfully trained and evaluated. The model demonstrated strong predictive performance on unseen data, with a low error rate.
