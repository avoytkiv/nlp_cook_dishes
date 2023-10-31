# nlp_cook_dishes

In this project, the run command will start the Jupyter notebook server on port 8888. By specifying ports: 8888, SkyPilot will expose port 8888 on the cluster, making the jupyter server publicly accessible. To launch and access the server, run:

```shell
sky launch -c jupyter jupyter.yaml
```

and look in for the logs for some output like:

```
Jupyter Server 2.7.0 is running at:
    http://127.0.0.1:8888/lab?token=<token>
```

To get the public IP address of the head node of the cluster, run `sky status --ip jupyter`.
In the jupyter server URL, replace `127.0.0.1` with the public IP from `sky status --ip jupyter` and open the URL in your browser.


Data source: https://www.kaggle.com/datasets/shuyangli94/food-com-recipes-and-user-interactions?select=PP_recipes.csv