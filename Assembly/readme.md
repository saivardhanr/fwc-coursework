# What is Assembly Language 
   let's <b>imagine</b> you're in a magical land of talking robots. These robots understand a language, but it's not like English or any language you speak. It's more like a secret code that only robots get.<br>

Now, Assembly Language is like the special way you talk to these robots. Instead of using long sentences, you give them short, specific commands. It's a bit like saying "Go forward 10 steps" or "Turn left" in a really concise and robot-friendly way.<br>

So, imagine you have a robot friend, and you want it to make a sandwich. Instead of saying,**"Hey robot, can you please go to the kitchen, find the bread, and put it on a plate?"** in a human language, you'd say in Assembly Language, **"Grab bread, put on plate."** It's like giving the robot direct, step-by-step instructions.<br>

People use Assembly Language when they need to be super clear and efficient in talking to computers or microcontrollers (tiny computers inside gadgets). **It's not the easiest language** for humans, but <b>it's perfect for making sure robots or computers understand exactly what to do!</b><br>

## How to upload to board Then ??
As we are using **Arduino Droid** and we cannot directly upload <b>.asm</b> file using it.<br>
We use **avra filename.asm**  to generate ,bin file from assembly file.<br>
If **avra** does not exist then install it using **apt install avra** <br>
After generating **.bin** file we can directly upload it using arduino droid,<br>
just head to <b> Menu --> Actions --> Upload --> Upload precompiled --> .bin file location --> Done</b>
