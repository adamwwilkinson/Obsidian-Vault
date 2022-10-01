# CAV Application

### Applications

#### Machine Learning
Can be used for simple machine learning.
```python
pip install sklearn
```

##### Setup ML Models
ML models need to learn, to do this we split our data to 80% training and 20% for validation.
```python
array = dataset.values
X = array[:, 0:4]
Y = array[:, 4]
X_train, X_validation, Y_train, Y_validation = \
	train_test_split(X, Y, test_size = 0.2, random_state = 1)
```
This only gathers the data and no training has occurred.

```python
def get_models():
	models = []
	models.append(('LR', LogisticRegression(solver='liblinear',multi_class='ovr')))
	models.append(('KNN', KNeighborsClassifier()))
	models.append(('SVM', SVC(gamm = 'auto')))
	return models

models = get_models()

def get_results(models, X_train, Y_train):
	results = []
	names = []
	print("Models    Accuracy (stdev)")
	for name, model in models:
		kfold = StratifiedKFold(n_splits = 10, random_state = 1, shuffle = True)
	   cv_results= cross_val_score\
		   (model,X_train,Y_train,cv=kfold,scoring='accurace')
	   results.append(cv_results)
	   names.append(name)
	   print('{:6}: {:10.4f} ({:.4f})'.format(name, cv_results.mean(), \
		   cv_results.std()))
		return (results, name)
results, names = get_results(models, X_train, Y_train)
```
To visualise:
```python
def vis_result(results, names):
	pyplot.boxplot(results, labels=names)
	pyplot.title('Algorithm Comparison')
	pyplot.show()

vis_result(results, names)
```

##### Predictions
We can use the best model above to make a prediction.
```python
def make_predictions(X_train, Y_train, X_validation, y_validation):
	model = SVC(gamma = 'auto')
	model.fit(X_train, Y_train)
	predictions = model.predict(X_validation)

	# Evaluate predictions
	print(accuracy_score(y_validation, predicions))
	print(confusion_matrix(y_validation, predictions))
	print(classification_report(y_validation, prediction))

	# Visualise confusion matrix
	disp = plot_confusion_matrix(model, X_validation, y_validation, \
		cmap=plt.cm.Blues, normalize = 'true')
	plt.show()

make_predictions(X_train, Y_train, X_validation, y_validation)
```

#### Visualising Data sets
Whether with [[Pandas]] or [[Numerical Python]], along with [[Visualisation in Python]].