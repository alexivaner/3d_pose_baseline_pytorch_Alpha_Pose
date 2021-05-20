

### Test

1. You can download the [pretrained model](https://drive.google.com/file/d/1NUY8oZoLKY9DP63Jg_ZE96_DEJKiVvRp/view?usp=sharing) on ground-truth 2d pose for a quick demo.

    ```
    python main.py --load $PATH_TO_gt_ckpt_best.pth.tar --test
    ```
    and you will get the results:

    |  | direct. | discuss. | eat. | greet. | phone | photo | pose | purch. | sit | sitd. | somke | wait | walkd. | walk | walkT | avg |
    | :--: | :--: | :--: | :--: | :--: |  :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
    | original version | 37.7 | 44.4 | 40.3 | 42.1 | 48.2 | 54.9 | 44.4 | 42.1 | 54.6 | 58.0 | 45.1 | 46.4 | 47.6 | 36.4 | 40.4 | 45.5|
    | pytorch version | 35.7 | 42.3 | 39.4 | 40.7 | 44.5 | 53.3 | 42.8 | 40.1 | 52.5 | 53.9 | 42.8 | 43.1 | 44.1 | 33.4 | 36.3 | - |
    

## License
MIT
