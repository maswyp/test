# test
video
clc,clear
file_path1 =  '.\0\';%
file_path2 =  '.\1\';%
img_path_list = dir(strcat(file_path1,'*.png'));%
img_path_list = sort_nat(img_path_list);%
img_num = length(img_path_list);%

aviobj=VideoWriter(strcat('.\avi\','Rabbit_double','.avi'));%文件名
aviobj.FrameRate=30;%
open(aviobj)
for i = 1:1:img_num
        %%
        image_name = img_path_list(i-1).name;%
        image_l =  imread(strcat(file_path1,image_name));
        %%
        image_h =  imread(strcat(file_path2,image_name));

        frame=[image_l,image_h];
        frame=uint8(frame);
        writeVideo(aviobj,frame); 
        disp(i)
end
close(aviobj)
























