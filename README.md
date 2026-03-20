# Class_ML

Train과 test의 카테고리가 동일한지 확인

```python
cols = train.select_dtypes(include='object').columns
for col in cols:
  set_train = set(train[col])
  set_test = set(test[col])
  same = (set_train==set_test)
  if not same:
    print(col,'카테고리 다름')
```

```python
#다른 게 없는 경우
train = pd.get_dummies(train)
test = pd.get_dummies(test)
```  

```python
#다른 게 존재할 경우 train과 test를 하나로 합쳐 원핫인코딩 실행
combined = pd.concat([train,test])
combined_dummies = pd.get_dummies(combined)
```

