# helm包创建和发布

## 一、创建仓库charts,勾选README.md

## 二、开启github page。Setting->page->build and deployment->branch->main. save.

## 三、生成charts包

```
git clone git@github.com:rouroumaibing/charts.git

cd charts

helm create demo

helm package demo

helm repo index .
```


## 四、推送到仓库

```
git add .

git commit -m "Add chart v0.1.0"

git push -u origin main
```

## 五、部署

```
helm repo add charts https://rouroumaibing.github.io/charts

helm search repo charts -l

helm install demo charts/demo
```