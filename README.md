# Coin identifier

Live currency identifier through video.

[View an example image here.](https://imgur.com/uTBTJau)

## The Algorithm

The code uses resnet18 to figure out patterns within the images that I provide. After training it to specifically look at the differences in the coins, I had it display the type of coin, along with its value in another box. I did this by using if statements and checking what the predictions were, if it labels the coin as a penny, the value is 0.01 and so on.

## Running this project

1. Download resnet18 and pytorch libraries before starting
2. After plugging in a camera to the nano, create a directiory using [mkdir -p ~/nvdli-data], after creating that directory, make a script to run a docker container using [echo "sudo docker run --runtime nvidia -it --rm --network host \
    --volume ~/nvdli-data:/nvdli-nano/data \
    --device /dev/video0 \
    nvcr.io/nvidia/dli/dli-nano-ai:v2.0.2-r32.7.1" > docker_dli_run.sh]
, after this you need to run this command to make it executable [chmod +x docker_dli_run.sh]. Lastly you need to run the script with [./docker_dli_run.sh]. It will tell you an html link with an ip, you need to put that into your browser. Then it will ask for a password, enter in [dlinano].
3. Next, you will need to download the ipynb file into the nano in the directory of your choice. In order to download this, you will need to use [wget https://github.com/JayJayGar/Nvidia_Project/archive/refs/heads/master.zip -O {Your_Name}.py].
4. After it is downloaded, you will need to go to the jupyter notebook that has been already been opened in your browser. You will need to run everything in order, and in the interactable box that pops up, you will need to load the model from where you have downloaded it.
5. And finally, you can use the indentifier as intended! Try pointing your camera at a penny or quarter!

[View a video explanation here](https://youtu.be/oLC2Z0s6jPY)
