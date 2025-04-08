# Helm package creation and publishing

## 1.Create a new repository "charts" and Add a README file

## 2.Open github page. Setting->page->build and deployment->branch->main. save.

## 3.Generate charts package

```
git clone git@github.com:rouroumaibing/charts.git

cd charts

helm create demo

helm package demo

helm repo index .
```


## 4. Push to github

```
git add .

git commit -m "Add chart v0.1.0"

git push -u origin main
```

## 5. Deployment

```
# index.html 404 Not Found，because GitHub has not yet released the GitHub page.

helm repo add charts https://rouroumaibing.github.io/charts

helm search repo charts -l | grep demo

# helm pull charts/demo

helm install demo charts/demo
```