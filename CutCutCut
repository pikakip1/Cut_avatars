from PIL import Image

image = Image.open('new.jpg')
image = image.convert('RGB')
red, green, blue, = image.split()

down = (50, 0, red.width - 50, red.height)
up = (100, 0, red.width, red.height)
img_base = red.crop(down)
img_up = red.crop(up)

shift_red = Image.blend(img_base, img_up, 0.5)
shift_red.save('shift_red.jpg')

down = (50, 0, blue.width - 50, blue.height)
up = (0, 0, blue.width-100, blue.height)
img_base = blue.crop(down)
img_up = blue.crop(up)

shift_blue = Image.blend(img_base, img_up, 0.5)
shift_blue.save('shift_blue.jpg')

img_green = green.crop(down)

end_image = Image.merge('RGB', (shift_red, shift_blue, img_green))

end_image.thumbnail((80, 80))
end_image.save('END_img.jpg')
