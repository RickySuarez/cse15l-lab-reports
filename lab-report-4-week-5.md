# Grep Command Options
* `-o`

  One issue with using the grep command is that you often get results containing multiple lines of code. However you may just want to find just the specific instance of a string. The `-o` command is very useful for that purpose.

  ## Example 1:

  ```
  [cs15lfa22nx@ieng6-201]:skill-demo1:504$ grep "studies" ./technical/biomed/rr74.txt
        circulation, and previous studies using NOS inhibitors [ 1,
        These discrepancies have been addressed in recent studies
        studies of 4 weeks of hypoxia in mature animals [ 9]. The
        [ 25, 26, 27]. Additionally, recent studies also suggest
        species and tissue specific. Previous studies of NOS
        previous studies, the plasma NO metabolite content in the
        considering studies using NOS-deficient mice. The present
  [cs15lfa22nx@ieng6-201]:skill-demo1:505$ grep -o "studies" ./technical/biomed/rr74.txt
  studies
  studies
  studies
  studies
  studies
  studies
  studies
  ```
  
  In this example we can see the difference between using `-o` and not using it. Normally the terminal outputs the entire line that a string appears in but using `-o` is helpful in that it only displays the actual strings that contains the argument.

  ## Example 2

  ```
  [cs15lfa22nx@ieng6-201]:skill-demo1:506$ grep -o "studies" ./technical/biomed/rr74.txt | wc
      7       7      56
  ```

  In this example, I used the command to search the `rr74.txt` file. I then used that results as the argument in the `wc` command in order to have it count the amount of times that string was used. This is helpful in see how many times that string was used.

  ## Example 3:

  ```
  cs15lfa22nx@ieng6-201]:skill-demo1:509$ grep -o "studies" ./technical/*/*.txt ./technical/*/*/*.txt | wc
   4685    4685  218765
   ```

   Similar to the last example, the result from `grep` was used as the argument in `wc`. The main difference however is that I was able to see how many times a word was used over several different `.txt` files by using `*` in the file paths.

   ---


  

* `-i`

    By adding -i in the grep command, all uppercase and lowercase characters will be ignored. This is helpful in finding any text that contains a string of characters regardless of capitilization. One example where this could be helpful is if you want to find all instances of the word "example" but also want to take into consideration the fact that the word could appear in the beginning of a sentence so you also want to find "Example." 
    
    ## Example 1:

    ```
    [cs15lfa22nx@ieng6-202]:Lab:511$ grep "BIOMED" find-results.txt
    [cs15lfa22nx@ieng6-202]:Lab:512$ grep -i "BIOMED" find-results.txt
    ./technical/biomed
    ./technical/biomed/1468-6708-3-1.txt
    ./technical/biomed/1468-6708-3-10.txt
    ./technical/biomed/1468-6708-3-3.txt
    ./technical/biomed/1468-6708-3-4.txt
    ./technical/biomed/1468-6708-3-7.txt
    ./technical/biomed/1471-2091-2-10.txt
    ./technical/biomed/1471-2091-2-11.txt
    ./technical/biomed/1471-2091-2-12.txt
    ./technical/biomed/1471-2091-2-13.txt
    ./technical/biomed/1471-2091-2-16.txt
    ./technical/biomed/1471-2091-2-5.txt
    ./technical/biomed/1471-2091-2-7.txt
    ./technical/biomed/1471-2091-2-9.txt
    ./technical/biomed/1471-2091-3-13.txt
    ./technical/biomed/1471-2091-3-14.txt
    ./technical/biomed/1471-2091-3-15.txt
    ./technical/biomed/1471-2091-3-16.txt
    ./technical/biomed/1471-2091-3-17.txt
    ./technical/biomed/1471-2091-3-18.txt
    ./technical/biomed/1471-2091-3-22.txt
    ./technical/biomed/1471-2091-3-23.txt
    ./technical/biomed/1471-2091-3-30.txt
    ./technical/biomed/1471-2091-3-31.txt
    ./technical/biomed/1471-2091-3-4.txt
    ./technical/biomed/1471-2091-3-8.txt
    ./technical/biomed/1471-2091-4-1.txt
    ./technical/biomed/1471-2091-4-5.txt
    ./technical/biomed/1471-2105-1-1.txt
    ./technical/biomed/1471-2105-2-1.txt
    ./technical/biomed/1471-2105-2-8.txt
    ./technical/biomed/1471-2105-2-9.txt
    ./technical/biomed/1471-2105-3-12.txt
    ./technical/biomed/1471-2105-3-14.txt
    ./technical/biomed/1471-2105-3-16.txt
    ./technical/biomed/1471-2105-3-17.txt
    ./technical/biomed/1471-2105-3-18.txt
    ./technical/biomed/1471-2105-3-2.txt
    ./technical/biomed/1471-2105-3-22.txt
    ./technical/biomed/1471-2105-3-23.txt
    ./technical/biomed/1471-2105-3-24.txt
    ./technical/biomed/1471-2105-3-26.txt
    ./technical/biomed/1471-2105-3-28.txt
    ./technical/biomed/1471-2105-3-3.txt
    ./technical/biomed/1471-2105-3-30.txt
    ./technical/biomed/1471-2105-3-34.txt
    ./technical/biomed/1471-2105-3-37.txt
    ./technical/biomed/1471-2105-3-38.txt
    ./technical/biomed/1471-2105-3-4.txt
    ./technical/biomed/1471-2105-3-6.txt
    ./technical/biomed/1471-2105-4-13.txt
    ./technical/biomed/1471-2105-4-24.txt
    ./technical/biomed/1471-2105-4-25.txt
    ./technical/biomed/1471-2105-4-26.txt
    ./technical/biomed/1471-2105-4-27.txt
    ./technical/biomed/1471-2105-4-28.txt
    ./technical/biomed/1471-2105-4-31.txt
    ./technical/biomed/1471-2121-1-2.txt
    ./technical/biomed/1471-2121-2-1.txt
    ./technical/biomed/1471-2121-2-10.txt
    ./technical/biomed/1471-2121-2-11.txt
    ./technical/biomed/1471-2121-2-12.txt
    ./technical/biomed/1471-2121-2-15.txt
    ./technical/biomed/1471-2121-2-18.txt
    ./technical/biomed/1471-2121-2-21.txt
    ./technical/biomed/1471-2121-2-22.txt
    ./technical/biomed/1471-2121-2-3.txt
    ./technical/biomed/1471-2121-2-6.txt
    ./technical/biomed/1471-2121-3-10.txt
    ./technical/biomed/1471-2121-3-11.txt
    ./technical/biomed/1471-2121-3-12.txt
    ./technical/biomed/1471-2121-3-13.txt
    ./technical/biomed/1471-2121-3-15.txt
    ./technical/biomed/1471-2121-3-16.txt
    ./technical/biomed/1471-2121-3-18.txt
    ./technical/biomed/1471-2121-3-19.txt
    ./technical/biomed/1471-2121-3-2.txt
    ./technical/biomed/1471-2121-3-21.txt
    ./technical/biomed/1471-2121-3-22.txt
    ./technical/biomed/1471-2121-3-25.txt
    ./technical/biomed/1471-2121-3-30.txt
    ./technical/biomed/1471-2121-3-4.txt
    ./technical/biomed/1471-2121-3-6.txt
    ./technical/biomed/1471-2121-3-8.txt
    ./technical/biomed/1471-2121-4-1.txt
    ./technical/biomed/1471-2121-4-2.txt
    ./technical/biomed/1471-2121-4-3.txt
    ./technical/biomed/1471-2121-4-4.txt
    ./technical/biomed/1471-2121-4-5.txt
    ./technical/biomed/1471-2121-4-6.txt
    ./technical/biomed/1471-213X-1-1.txt
    ./technical/biomed/1471-213X-1-10.txt
    ./technical/biomed/1471-213X-1-11.txt
    ./technical/biomed/1471-213X-1-12.txt
    ./technical/biomed/1471-213X-1-13.txt
    ./technical/biomed/1471-213X-1-15.txt
    ./technical/biomed/1471-213X-1-2.txt
    ./technical/biomed/1471-213X-1-3.txt
    ./technical/biomed/1471-213X-1-4.txt
    ./technical/biomed/1471-213X-1-6.txt
    ./technical/biomed/1471-213X-1-9.txt
    ./technical/biomed/1471-213X-2-1.txt
    ./technical/biomed/1471-213X-2-7.txt
    ./technical/biomed/1471-213X-2-8.txt
    ./technical/biomed/1471-213X-3-2.txt
    ./technical/biomed/1471-213X-3-3.txt
    ./technical/biomed/1471-213X-3-4.txt
    ./technical/biomed/1471-213X-3-7.txt
    ./technical/biomed/1471-2148-1-1.txt
    ./technical/biomed/1471-2148-1-14.txt
    ./technical/biomed/1471-2148-1-4.txt
    ./technical/biomed/1471-2148-1-6.txt
    ./technical/biomed/1471-2148-1-8.txt
    ./technical/biomed/1471-2148-2-12.txt
    ./technical/biomed/1471-2148-2-14.txt
    ./technical/biomed/1471-2148-2-15.txt
    ./technical/biomed/1471-2148-2-17.txt
    ./technical/biomed/1471-2148-2-2.txt
    ./technical/biomed/1471-2148-2-5.txt
    ./technical/biomed/1471-2148-2-7.txt
    ./technical/biomed/1471-2148-2-8.txt
    ./technical/biomed/1471-2148-3-1.txt
    ./technical/biomed/1471-2148-3-18.txt
    ./technical/biomed/1471-2148-3-3.txt
    ./technical/biomed/1471-2148-3-4.txt
    ./technical/biomed/1471-2148-3-7.txt
    ./technical/biomed/1471-2156-2-1.txt
    ./technical/biomed/1471-2156-2-12.txt
    ./technical/biomed/1471-2156-2-17.txt
    ./technical/biomed/1471-2156-2-18.txt
    ./technical/biomed/1471-2156-2-3.txt
    ./technical/biomed/1471-2156-2-5.txt
    ./technical/biomed/1471-2156-2-7.txt
    ./technical/biomed/1471-2156-2-8.txt
    ./technical/biomed/1471-2156-3-10.txt
    ./technical/biomed/1471-2156-3-11.txt
    ./technical/biomed/1471-2156-3-16.txt
    ./technical/biomed/1471-2156-3-17.txt
    ./technical/biomed/1471-2156-3-22.txt
    ./technical/biomed/1471-2156-3-3.txt
    ./technical/biomed/1471-2156-3-4.txt
    ./technical/biomed/1471-2156-4-10.txt
    ./technical/biomed/1471-2156-4-5.txt
    ./technical/biomed/1471-2156-4-6.txt
    ./technical/biomed/1471-2156-4-9.txt
    ./technical/biomed/1471-2164-2-1.txt
    ./technical/biomed/1471-2164-2-2.txt
    ./technical/biomed/1471-2164-2-4.txt
    ./technical/biomed/1471-2164-2-6.txt
    ./technical/biomed/1471-2164-2-7.txt
    ./technical/biomed/1471-2164-2-8.txt
    ./technical/biomed/1471-2164-2-9.txt
    ./technical/biomed/1471-2164-3-1.txt
    ./technical/biomed/1471-2164-3-10.txt
    ./technical/biomed/1471-2164-3-13.txt
    ./technical/biomed/1471-2164-3-15.txt
    ./technical/biomed/1471-2164-3-16.txt
    ./technical/biomed/1471-2164-3-18.txt
    ./technical/biomed/1471-2164-3-19.txt
    ./technical/biomed/1471-2164-3-23.txt
    ./technical/biomed/1471-2164-3-24.txt
    ./technical/biomed/1471-2164-3-26.txt
    ./technical/biomed/1471-2164-3-27.txt
    ./technical/biomed/1471-2164-3-28.txt
    ./technical/biomed/1471-2164-3-29.txt
    ./technical/biomed/1471-2164-3-30.txt
    ./technical/biomed/1471-2164-3-31.txt
    ./technical/biomed/1471-2164-3-32.txt
    ./technical/biomed/1471-2164-3-33.txt
    ./technical/biomed/1471-2164-3-34.txt
    ./technical/biomed/1471-2164-3-35.txt
    ./technical/biomed/1471-2164-3-4.txt
    ./technical/biomed/1471-2164-3-6.txt
    ./technical/biomed/1471-2164-3-7.txt
    ./technical/biomed/1471-2164-3-8.txt
    ./technical/biomed/1471-2164-3-9.txt
    ./technical/biomed/1471-2164-4-13.txt
    ./technical/biomed/1471-2164-4-14.txt
    ./technical/biomed/1471-2164-4-15.txt
    ./technical/biomed/1471-2164-4-16.txt
    ./technical/biomed/1471-2164-4-19.txt
    ./technical/biomed/1471-2164-4-2.txt
    ./technical/biomed/1471-2164-4-21.txt
    ./technical/biomed/1471-2164-4-22.txt
    ./technical/biomed/1471-2164-4-23.txt
    ./technical/biomed/1471-2164-4-24.txt
    ./technical/biomed/1471-2164-4-25.txt
    ./technical/biomed/1471-2164-4-26.txt
    ./technical/biomed/1471-2164-4-28.txt
    ./technical/biomed/1471-2164-4-4.txt
    ./technical/biomed/1471-2164-4-5.txt
    ./technical/biomed/1471-2164-4-6.txt
    ./technical/biomed/1471-2172-1-1.txt
    ./technical/biomed/1471-2172-2-10.txt
    ./technical/biomed/1471-2172-2-3.txt
    ./technical/biomed/1471-2172-2-4.txt
    ./technical/biomed/1471-2172-2-9.txt
    ./technical/biomed/1471-2172-3-1.txt
    ./technical/biomed/1471-2172-3-10.txt
    ./technical/biomed/1471-2172-3-12.txt
    ./technical/biomed/1471-2172-3-16.txt
    ./technical/biomed/1471-2172-3-2.txt
    ./technical/biomed/1471-2172-3-4.txt
    ./technical/biomed/1471-2172-3-9.txt
    ./technical/biomed/1471-2172-4-1.txt
    ./technical/biomed/1471-2172-4-2.txt
    ./technical/biomed/1471-2180-1-12.txt
    ./technical/biomed/1471-2180-1-16.txt
    ./technical/biomed/1471-2180-1-26.txt
    ./technical/biomed/1471-2180-1-28.txt
    ./technical/biomed/1471-2180-1-29.txt
    ./technical/biomed/1471-2180-1-31.txt
    ./technical/biomed/1471-2180-1-33.txt
    ./technical/biomed/1471-2180-1-34.txt
    ./technical/biomed/1471-2180-1-7.txt
    ./technical/biomed/1471-2180-1-8.txt
    ./technical/biomed/1471-2180-2-1.txt
    ./technical/biomed/1471-2180-2-13.txt
    ./technical/biomed/1471-2180-2-16.txt
    ./technical/biomed/1471-2180-2-2.txt
    ./technical/biomed/1471-2180-2-20.txt
    ./technical/biomed/1471-2180-2-22.txt
    ./technical/biomed/1471-2180-2-26.txt
    ./technical/biomed/1471-2180-2-29.txt
    ./technical/biomed/1471-2180-2-32.txt
    ./technical/biomed/1471-2180-2-35.txt
    ./technical/biomed/1471-2180-2-38.txt
    ./technical/biomed/1471-2180-2-7.txt
    ./technical/biomed/1471-2180-3-10.txt
    ./technical/biomed/1471-2180-3-11.txt
    ./technical/biomed/1471-2180-3-13.txt
    ./technical/biomed/1471-2180-3-15.txt
    ./technical/biomed/1471-2180-3-4.txt
    ./technical/biomed/1471-2180-3-5.txt
    ./technical/biomed/1471-2180-3-9.txt
    ./technical/biomed/1471-2199-2-1.txt
    ./technical/biomed/1471-2199-2-10.txt
    ./technical/biomed/1471-2199-2-12.txt
    ./technical/biomed/1471-2199-2-2.txt
    ./technical/biomed/1471-2199-2-3.txt
    ./technical/biomed/1471-2199-2-4.txt
    ./technical/biomed/1471-2199-2-5.txt
    ./technical/biomed/1471-2199-2-6.txt
    ./technical/biomed/1471-2199-3-10.txt
    ./technical/biomed/1471-2199-3-11.txt
    ./technical/biomed/1471-2199-3-12.txt
    ./technical/biomed/1471-2199-3-17.txt
    ./technical/biomed/1471-2199-3-3.txt
    ./technical/biomed/1471-2199-3-7.txt
    ./technical/biomed/1471-2199-4-4.txt
    ./technical/biomed/1471-2199-4-5.txt
    ./technical/biomed/1471-2202-1-1.txt
    ./technical/biomed/1471-2202-2-1.txt
    ./technical/biomed/1471-2202-2-10.txt
    ./technical/biomed/1471-2202-2-12.txt
    ./technical/biomed/1471-2202-2-14.txt
    ./technical/biomed/1471-2202-2-15.txt
    ./technical/biomed/1471-2202-2-16.txt
    ./technical/biomed/1471-2202-2-17.txt
    ./technical/biomed/1471-2202-2-18.txt
    ./technical/biomed/1471-2202-2-19.txt
    ./technical/biomed/1471-2202-2-2.txt
    ./technical/biomed/1471-2202-2-20.txt
    ./technical/biomed/1471-2202-2-3.txt
    ./technical/biomed/1471-2202-2-5.txt
    ./technical/biomed/1471-2202-2-6.txt
    ./technical/biomed/1471-2202-2-7.txt
    ./technical/biomed/1471-2202-2-8.txt
    ./technical/biomed/1471-2202-2-9.txt
    ./technical/biomed/1471-2202-3-1.txt
    ./technical/biomed/1471-2202-3-10.txt
    ./technical/biomed/1471-2202-3-11.txt
    ./technical/biomed/1471-2202-3-14.txt
    ./technical/biomed/1471-2202-3-16.txt
    ./technical/biomed/1471-2202-3-17.txt
    ./technical/biomed/1471-2202-3-19.txt
    ./technical/biomed/1471-2202-3-20.txt
    ./technical/biomed/1471-2202-3-3.txt
    ./technical/biomed/1471-2202-3-4.txt
    ./technical/biomed/1471-2202-3-5.txt
    ./technical/biomed/1471-2202-3-7.txt
    ./technical/biomed/1471-2202-3-8.txt
    ./technical/biomed/1471-2202-4-10.txt
    ./technical/biomed/1471-2202-4-11.txt
    ./technical/biomed/1471-2202-4-12.txt
    ./technical/biomed/1471-2202-4-16.txt
    ./technical/biomed/1471-2202-4-17.txt
    ./technical/biomed/1471-2202-4-2.txt
    ./technical/biomed/1471-2202-4-3.txt
    ./technical/biomed/1471-2202-4-5.txt
    ./technical/biomed/1471-2202-4-6.txt
    ./technical/biomed/1471-2210-1-10.txt
    ./technical/biomed/1471-2210-1-2.txt
    ./technical/biomed/1471-2210-1-3.txt
    ./technical/biomed/1471-2210-1-4.txt
    ./technical/biomed/1471-2210-1-7.txt
    ./technical/biomed/1471-2210-1-8.txt
    ./technical/biomed/1471-2210-2-14.txt
    ./technical/biomed/1471-2210-2-4.txt
    ./technical/biomed/1471-2210-2-5.txt
    ./technical/biomed/1471-2210-2-6.txt
    ./technical/biomed/1471-2210-2-8.txt
    ./technical/biomed/1471-2210-2-9.txt
    ./technical/biomed/1471-2210-3-1.txt
    ./technical/biomed/1471-2210-3-3.txt
    ./technical/biomed/1471-2229-1-2.txt
    ./technical/biomed/1471-2229-1-3.txt
    ./technical/biomed/1471-2229-2-11.txt
    ./technical/biomed/1471-2229-2-3.txt
    ./technical/biomed/1471-2229-2-4.txt
    ./technical/biomed/1471-2229-2-8.txt
    ./technical/biomed/1471-2229-2-9.txt
    ./technical/biomed/1471-2229-3-3.txt
    ./technical/biomed/1471-2253-1-1.txt
    ./technical/biomed/1471-2253-2-4.txt
    ./technical/biomed/1471-2253-2-5.txt
    ./technical/biomed/1471-2261-1-6.txt
    ./technical/biomed/1471-2261-2-11.txt
    ./technical/biomed/1471-2261-3-4.txt
    ./technical/biomed/1471-2261-3-5.txt
    ./technical/biomed/1471-2288-1-9.txt
    ./technical/biomed/1471-2288-2-10.txt
    ./technical/biomed/1471-2288-2-11.txt
    ./technical/biomed/1471-2288-2-4.txt
    ./technical/biomed/1471-2288-3-4.txt
    ./technical/biomed/1471-2288-3-8.txt
    ./technical/biomed/1471-2288-3-9.txt
    ./technical/biomed/1471-2296-3-18.txt
    ./technical/biomed/1471-2296-3-19.txt
    ./technical/biomed/1471-2296-3-3.txt
    ./technical/biomed/1471-230X-1-10.txt
    ./technical/biomed/1471-230X-1-5.txt
    ./technical/biomed/1471-230X-1-6.txt
    ./technical/biomed/1471-230X-1-8.txt
    ./technical/biomed/1471-230X-2-17.txt
    ./technical/biomed/1471-230X-2-21.txt
    ./technical/biomed/1471-230X-2-23.txt
    ./technical/biomed/1471-230X-3-3.txt
    ./technical/biomed/1471-230X-3-5.txt
    ./technical/biomed/1471-2318-3-2.txt
    ./technical/biomed/1471-2326-2-4.txt
    ./technical/biomed/1471-2334-1-10.txt
    ./technical/biomed/1471-2334-1-13.txt
    ./technical/biomed/1471-2334-1-17.txt
    ./technical/biomed/1471-2334-1-21.txt
    ./technical/biomed/1471-2334-1-24.txt
    ./technical/biomed/1471-2334-1-9.txt
    ./technical/biomed/1471-2334-2-1.txt
    ./technical/biomed/1471-2334-2-24.txt
    ./technical/biomed/1471-2334-2-26.txt
    ./technical/biomed/1471-2334-2-27.txt
    ./technical/biomed/1471-2334-2-29.txt
    ./technical/biomed/1471-2334-2-5.txt
    ./technical/biomed/1471-2334-2-6.txt
    ./technical/biomed/1471-2334-2-7.txt
    ./technical/biomed/1471-2334-3-10.txt
    ./technical/biomed/1471-2334-3-11.txt
    ./technical/biomed/1471-2334-3-12.txt
    ./technical/biomed/1471-2334-3-13.txt
    ./technical/biomed/1471-2334-3-15.txt
    ./technical/biomed/1471-2334-3-9.txt
    ./technical/biomed/1471-2350-2-11.txt
    ./technical/biomed/1471-2350-2-12.txt
    ./technical/biomed/1471-2350-2-2.txt
    ./technical/biomed/1471-2350-2-8.txt
    ./technical/biomed/1471-2350-3-1.txt
    ./technical/biomed/1471-2350-3-12.txt
    ./technical/biomed/1471-2350-3-7.txt
    ./technical/biomed/1471-2350-3-9.txt
    ./technical/biomed/1471-2350-4-2.txt
    ./technical/biomed/1471-2350-4-3.txt
    ./technical/biomed/1471-2350-4-4.txt
    ./technical/biomed/1471-2350-4-6.txt
    ./technical/biomed/1471-2369-3-1.txt
    ./technical/biomed/1471-2369-3-10.txt
    ./technical/biomed/1471-2369-3-6.txt
    ./technical/biomed/1471-2369-3-9.txt
    ./technical/biomed/1471-2369-4-1.txt
    ./technical/biomed/1471-2369-4-5.txt
    ./technical/biomed/1471-2377-1-2.txt
    ./technical/biomed/1471-2377-2-4.txt
    ./technical/biomed/1471-2377-2-6.txt
    ./technical/biomed/1471-2377-3-4.txt
    ./technical/biomed/1471-2407-1-13.txt
    ./technical/biomed/1471-2407-1-15.txt
    ./technical/biomed/1471-2407-1-19.txt
    ./technical/biomed/1471-2407-1-6.txt
    ./technical/biomed/1471-2407-2-11.txt
    ./technical/biomed/1471-2407-2-12.txt
    ./technical/biomed/1471-2407-2-15.txt
    ./technical/biomed/1471-2407-2-16.txt
    ./technical/biomed/1471-2407-2-17.txt
    ./technical/biomed/1471-2407-2-18.txt
    ./technical/biomed/1471-2407-2-19.txt
    ./technical/biomed/1471-2407-2-22.txt
    ./technical/biomed/1471-2407-2-23.txt
    ./technical/biomed/1471-2407-2-3.txt
    ./technical/biomed/1471-2407-2-31.txt
    ./technical/biomed/1471-2407-2-33.txt
    ./technical/biomed/1471-2407-2-8.txt
    ./technical/biomed/1471-2407-2-9.txt
    ./technical/biomed/1471-2407-3-14.txt
    ./technical/biomed/1471-2407-3-15.txt
    ./technical/biomed/1471-2407-3-16.txt
    ./technical/biomed/1471-2407-3-18.txt
    ./technical/biomed/1471-2407-3-3.txt
    ./technical/biomed/1471-2407-3-4.txt
    ./technical/biomed/1471-2407-3-5.txt
    ./technical/biomed/1471-2415-3-1.txt
    ./technical/biomed/1471-2415-3-3.txt
    ./technical/biomed/1471-2415-3-4.txt
    ./technical/biomed/1471-2415-3-5.txt
    ./technical/biomed/1471-2431-2-1.txt
    ./technical/biomed/1471-2431-2-11.txt
    ./technical/biomed/1471-2431-2-12.txt
    ./technical/biomed/1471-2431-2-4.txt
    ./technical/biomed/1471-2431-3-3.txt
    ./technical/biomed/1471-2431-3-4.txt
    ./technical/biomed/1471-2431-3-5.txt
    ./technical/biomed/1471-2431-3-6.txt
    ./technical/biomed/1471-244X-2-9.txt
    ./technical/biomed/1471-244X-3-5.txt
    ./technical/biomed/1471-2458-1-9.txt
    ./technical/biomed/1471-2458-2-11.txt
    ./technical/biomed/1471-2458-2-16.txt
    ./technical/biomed/1471-2458-2-18.txt
    ./technical/biomed/1471-2458-2-21.txt
    ./technical/biomed/1471-2458-2-25.txt
    ./technical/biomed/1471-2458-2-3.txt
    ./technical/biomed/1471-2458-2-6.txt
    ./technical/biomed/1471-2458-3-11.txt
    ./technical/biomed/1471-2458-3-2.txt
    ./technical/biomed/1471-2458-3-20.txt
    ./technical/biomed/1471-2458-3-5.txt
    ./technical/biomed/1471-2458-3-9.txt
    ./technical/biomed/1471-2466-1-1.txt
    ./technical/biomed/1471-2466-2-3.txt
    ./technical/biomed/1471-2466-2-4.txt
    ./technical/biomed/1471-2466-3-1.txt
    ./technical/biomed/1471-2474-2-1.txt
    ./technical/biomed/1471-2474-2-2.txt
    ./technical/biomed/1471-2474-2-3.txt
    ./technical/biomed/1471-2474-3-23.txt
    ./technical/biomed/1471-2474-3-3.txt
    ./technical/biomed/1471-2474-4-4.txt
    ./technical/biomed/1471-2474-4-8.txt
    ./technical/biomed/1471-2490-3-2.txt
    ./technical/biomed/1471-5945-1-3.txt
    ./technical/biomed/1471-5945-2-13.txt
    ./technical/biomed/1471-5945-3-3.txt
    ./technical/biomed/1472-6750-1-11.txt
    ./technical/biomed/1472-6750-1-12.txt
    ./technical/biomed/1472-6750-1-13.txt
    ./technical/biomed/1472-6750-1-6.txt
    ./technical/biomed/1472-6750-1-8.txt
    ./technical/biomed/1472-6750-2-10.txt
    ./technical/biomed/1472-6750-2-13.txt
    ./technical/biomed/1472-6750-2-14.txt
    ./technical/biomed/1472-6750-2-2.txt
    ./technical/biomed/1472-6750-2-21.txt
    ./technical/biomed/1472-6750-3-11.txt
    ./technical/biomed/1472-6750-3-4.txt
    ./technical/biomed/1472-6750-3-6.txt
    ./technical/biomed/1472-6769-1-1.txt
    ./technical/biomed/1472-6769-1-2.txt
    ./technical/biomed/1472-6769-1-3.txt
    ./technical/biomed/1472-6769-1-4.txt
    ./technical/biomed/1472-6785-1-3.txt
    ./technical/biomed/1472-6785-1-5.txt
    ./technical/biomed/1472-6785-2-6.txt
    ./technical/biomed/1472-6785-2-7.txt
    ./technical/biomed/1472-6793-1-11.txt
    ./technical/biomed/1472-6793-1-12.txt
    ./technical/biomed/1472-6793-1-15.txt
    ./technical/biomed/1472-6793-1-2.txt
    ./technical/biomed/1472-6793-1-6.txt
    ./technical/biomed/1472-6793-1-8.txt
    ./technical/biomed/1472-6793-2-1.txt
    ./technical/biomed/1472-6793-2-11.txt
    ./technical/biomed/1472-6793-2-16.txt
    ./technical/biomed/1472-6793-2-17.txt
    ./technical/biomed/1472-6793-2-18.txt
    ./technical/biomed/1472-6793-2-19.txt
    ./technical/biomed/1472-6793-2-2.txt
    ./technical/biomed/1472-6793-2-4.txt
    ./technical/biomed/1472-6793-2-5.txt
    ./technical/biomed/1472-6793-2-8.txt
    ./technical/biomed/1472-6793-3-3.txt
    ./technical/biomed/1472-6793-3-4.txt
    ./technical/biomed/1472-6793-3-5.txt
    ./technical/biomed/1472-6793-3-6.txt
    ./technical/biomed/1472-6807-1-1.txt
    ./technical/biomed/1472-6807-2-1.txt
    ./technical/biomed/1472-6807-2-2.txt
    ./technical/biomed/1472-6807-2-3.txt
    ./technical/biomed/1472-6807-2-4.txt
    ./technical/biomed/1472-6807-2-5.txt
    ./technical/biomed/1472-6807-2-9.txt
    ./technical/biomed/1472-6807-3-1.txt
    ./technical/biomed/1472-6807-3-2.txt
    ./technical/biomed/1472-6815-2-3.txt
    ./technical/biomed/1472-6823-2-2.txt
    ./technical/biomed/1472-6823-3-1.txt
    ./technical/biomed/1472-6831-2-2.txt
    ./technical/biomed/1472-6831-3-1.txt
    ./technical/biomed/1472-684X-1-5.txt
    ./technical/biomed/1472-684X-2-1.txt
    ./technical/biomed/1472-684X-2-2.txt
    ./technical/biomed/1472-6874-2-1.txt
    ./technical/biomed/1472-6874-2-13.txt
    ./technical/biomed/1472-6874-2-8.txt
    ./technical/biomed/1472-6874-3-2.txt
    ./technical/biomed/1472-6882-1-10.txt
    ./technical/biomed/1472-6882-1-11.txt
    ./technical/biomed/1472-6882-1-12.txt
    ./technical/biomed/1472-6882-1-7.txt
    ./technical/biomed/1472-6882-2-10.txt
    ./technical/biomed/1472-6882-2-5.txt
    ./technical/biomed/1472-6882-3-1.txt
    ./technical/biomed/1472-6882-3-3.txt
    ./technical/biomed/1472-6890-1-4.txt
    ./technical/biomed/1472-6890-2-5.txt
    ./technical/biomed/1472-6890-3-2.txt
    ./technical/biomed/1472-6904-1-2.txt
    ./technical/biomed/1472-6904-2-4.txt
    ./technical/biomed/1472-6904-2-5.txt
    ./technical/biomed/1472-6904-2-7.txt
    ./technical/biomed/1472-6904-3-1.txt
    ./technical/biomed/1472-6920-1-3.txt
    ./technical/biomed/1472-6920-2-1.txt
    ./technical/biomed/1472-6920-2-3.txt
    ./technical/biomed/1472-6947-1-2.txt
    ./technical/biomed/1472-6947-1-5.txt
    ./technical/biomed/1472-6947-1-6.txt
    ./technical/biomed/1472-6947-2-4.txt
    ./technical/biomed/1472-6947-2-7.txt
    ./technical/biomed/1472-6947-3-5.txt
    ./technical/biomed/1472-6947-3-8.txt
    ./technical/biomed/1472-6955-2-1.txt
    ./technical/biomed/1472-6963-1-11.txt
    ./technical/biomed/1472-6963-1-8.txt
    ./technical/biomed/1472-6963-2-10.txt
    ./technical/biomed/1472-6963-3-1.txt
    ./technical/biomed/1472-6963-3-11.txt
    ./technical/biomed/1472-6963-3-12.txt
    ./technical/biomed/1472-6963-3-13.txt
    ./technical/biomed/1472-6963-3-14.txt
    ./technical/biomed/1472-6963-3-6.txt
    ./technical/biomed/1472-6963-3-7.txt
    ./technical/biomed/1475-2832-1-1.txt
    ./technical/biomed/1475-2867-2-10.txt
    ./technical/biomed/1475-2867-2-15.txt
    ./technical/biomed/1475-2867-2-7.txt
    ./technical/biomed/1475-2867-3-12.txt
    ./technical/biomed/1475-2867-3-2.txt
    ./technical/biomed/1475-2867-3-3.txt
    ./technical/biomed/1475-2867-3-4.txt
    ./technical/biomed/1475-2875-1-14.txt
    ./technical/biomed/1475-2875-1-5.txt
    ./technical/biomed/1475-2875-2-10.txt
    ./technical/biomed/1475-2875-2-14.txt
    ./technical/biomed/1475-2875-2-4.txt
    ./technical/biomed/1475-2883-2-11.txt
    ./technical/biomed/1475-2891-1-2.txt
    ./technical/biomed/1475-2891-2-1.txt
    ./technical/biomed/1475-4924-1-10.txt
    ./technical/biomed/1475-4924-1-5.txt
    ./technical/biomed/1475-925X-2-1.txt
    ./technical/biomed/1475-925X-2-10.txt
    ./technical/biomed/1475-925X-2-11.txt
    ./technical/biomed/1475-925X-2-12.txt
    ./technical/biomed/1475-925X-2-3.txt
    ./technical/biomed/1475-925X-2-6.txt
    ./technical/biomed/1475-9268-1-1.txt
    ./technical/biomed/1475-9268-1-2.txt
    ./technical/biomed/1475-9276-1-3.txt
    ./technical/biomed/1476-069X-1-3.txt
    ./technical/biomed/1476-069X-2-2.txt
    ./technical/biomed/1476-069X-2-4.txt
    ./technical/biomed/1476-069X-2-7.txt
    ./technical/biomed/1476-069X-2-9.txt
    ./technical/biomed/1476-0711-2-3.txt
    ./technical/biomed/1476-0711-2-7.txt
    ./technical/biomed/1476-072X-2-3.txt
    ./technical/biomed/1476-072X-2-4.txt
    ./technical/biomed/1476-4598-1-3.txt
    ./technical/biomed/1476-4598-1-5.txt
    ./technical/biomed/1476-4598-1-6.txt
    ./technical/biomed/1476-4598-1-8.txt
    ./technical/biomed/1476-4598-2-1.txt
    ./technical/biomed/1476-4598-2-2.txt
    ./technical/biomed/1476-4598-2-20.txt
    ./technical/biomed/1476-4598-2-22.txt
    ./technical/biomed/1476-4598-2-24.txt
    ./technical/biomed/1476-4598-2-25.txt
    ./technical/biomed/1476-4598-2-28.txt
    ./technical/biomed/1476-4598-2-3.txt
    ./technical/biomed/1476-511X-1-2.txt
    ./technical/biomed/1476-511X-2-2.txt
    ./technical/biomed/1476-511X-2-3.txt
    ./technical/biomed/1476-5918-1-2.txt
    ./technical/biomed/1476-9433-1-2.txt
    ./technical/biomed/1476-9433-1-3.txt
    ./technical/biomed/1477-5956-1-1.txt
    ./technical/biomed/1477-7525-1-10.txt
    ./technical/biomed/1477-7525-1-12.txt
    ./technical/biomed/1477-7525-1-9.txt
    ./technical/biomed/1477-7819-1-10.txt
    ./technical/biomed/1477-7827-1-13.txt
    ./technical/biomed/1477-7827-1-17.txt
    ./technical/biomed/1477-7827-1-21.txt
    ./technical/biomed/1477-7827-1-23.txt
    ./technical/biomed/1477-7827-1-27.txt
    ./technical/biomed/1477-7827-1-31.txt
    ./technical/biomed/1477-7827-1-36.txt
    ./technical/biomed/1477-7827-1-43.txt
    ./technical/biomed/1477-7827-1-46.txt
    ./technical/biomed/1477-7827-1-48.txt
    ./technical/biomed/1477-7827-1-54.txt
    ./technical/biomed/1477-7827-1-6.txt
    ./technical/biomed/1477-7827-1-9.txt
    ./technical/biomed/1478-1336-1-2.txt
    ./technical/biomed/1478-1336-1-3.txt
    ./technical/biomed/1478-1336-1-4.txt
    ./technical/biomed/1478-7954-1-3.txt
    ./technical/biomed/ar104.txt
    ./technical/biomed/ar118.txt
    ./technical/biomed/ar120.txt
    ./technical/biomed/ar130.txt
    ./technical/biomed/ar140.txt
    ./technical/biomed/ar149.txt
    ./technical/biomed/ar297.txt
    ./technical/biomed/ar309.txt
    ./technical/biomed/ar319.txt
    ./technical/biomed/ar321.txt
    ./technical/biomed/ar328.txt
    ./technical/biomed/ar331.txt
    ./technical/biomed/ar383.txt
    ./technical/biomed/ar387.txt
    ./technical/biomed/ar407.txt
    ./technical/biomed/ar408.txt
    ./technical/biomed/ar409.txt
    ./technical/biomed/ar422.txt
    ./technical/biomed/ar429.txt
    ./technical/biomed/ar430.txt
    ./technical/biomed/ar601.txt
    ./technical/biomed/ar612.txt
    ./technical/biomed/ar615.txt
    ./technical/biomed/ar619.txt
    ./technical/biomed/ar624.txt
    ./technical/biomed/ar68.txt
    ./technical/biomed/ar745.txt
    ./technical/biomed/ar750.txt
    ./technical/biomed/ar774.txt
    ./technical/biomed/ar778.txt
    ./technical/biomed/ar79.txt
    ./technical/biomed/ar792.txt
    ./technical/biomed/ar795.txt
    ./technical/biomed/ar799.txt
    ./technical/biomed/ar93.txt
    ./technical/biomed/bcr273.txt
    ./technical/biomed/bcr284.txt
    ./technical/biomed/bcr285.txt
    ./technical/biomed/bcr294.txt
    ./technical/biomed/bcr303.txt
    ./technical/biomed/bcr317.txt
    ./technical/biomed/bcr45.txt
    ./technical/biomed/bcr458.txt
    ./technical/biomed/bcr567.txt
    ./technical/biomed/bcr568.txt
    ./technical/biomed/bcr570.txt
    ./technical/biomed/bcr571.txt
    ./technical/biomed/bcr583.txt
    ./technical/biomed/bcr588.txt
    ./technical/biomed/bcr602.txt
    ./technical/biomed/bcr605.txt
    ./technical/biomed/bcr607.txt
    ./technical/biomed/bcr618.txt
    ./technical/biomed/bcr620.txt
    ./technical/biomed/bcr631.txt
    ./technical/biomed/bcr635.txt
    ./technical/biomed/cc103.txt
    ./technical/biomed/cc1044.txt
    ./technical/biomed/cc105.txt
    ./technical/biomed/cc1476.txt
    ./technical/biomed/cc1477.txt
    ./technical/biomed/cc1495.txt
    ./technical/biomed/cc1497.txt
    ./technical/biomed/cc1498.txt
    ./technical/biomed/cc1529.txt
    ./technical/biomed/cc1538.txt
    ./technical/biomed/cc1547.txt
    ./technical/biomed/cc1843.txt
    ./technical/biomed/cc1852.txt
    ./technical/biomed/cc1856.txt
    ./technical/biomed/cc1882.txt
    ./technical/biomed/cc2160.txt
    ./technical/biomed/cc2167.txt
    ./technical/biomed/cc2171.txt
    ./technical/biomed/cc2172.txt
    ./technical/biomed/cc2190.txt
    ./technical/biomed/cc2358.txt
    ./technical/biomed/cc3.txt
    ./technical/biomed/cc300.txt
    ./technical/biomed/cc303.txt
    ./technical/biomed/cc343.txt
    ./technical/biomed/cc350.txt
    ./technical/biomed/cc367.txt
    ./technical/biomed/cc4.txt
    ./technical/biomed/cc713.txt
    ./technical/biomed/cc973.txt
    ./technical/biomed/cc991.txt
    ./technical/biomed/cvm-2-1-038.txt
    ./technical/biomed/cvm-2-4-180.txt
    ./technical/biomed/cvm-2-4-187.txt
    ./technical/biomed/cvm-2-6-278.txt
    ./technical/biomed/cvm-2-6-286.txt
    ./technical/biomed/gb-2000-1-1-research002.txt
    ./technical/biomed/gb-2000-1-2-research0003.txt
    ./technical/biomed/gb-2001-2-10-research0041.txt
    ./technical/biomed/gb-2001-2-10-research0042.txt
    ./technical/biomed/gb-2001-2-11-research0045.txt
    ./technical/biomed/gb-2001-2-11-research0046.txt
    ./technical/biomed/gb-2001-2-12-research0051.txt
    ./technical/biomed/gb-2001-2-12-research0053.txt
    ./technical/biomed/gb-2001-2-12-research0054.txt
    ./technical/biomed/gb-2001-2-12-research0055.txt
    ./technical/biomed/gb-2001-2-2-research0004.txt
    ./technical/biomed/gb-2001-2-3-research0007.txt
    ./technical/biomed/gb-2001-2-3-research0008.txt
    ./technical/biomed/gb-2001-2-4-research0010.txt
    ./technical/biomed/gb-2001-2-4-research0011.txt
    ./technical/biomed/gb-2001-2-4-research0012.txt
    ./technical/biomed/gb-2001-2-4-research0014.txt
    ./technical/biomed/gb-2001-2-6-research0018.txt
    ./technical/biomed/gb-2001-2-6-research0020.txt
    ./technical/biomed/gb-2001-2-6-research0021.txt
    ./technical/biomed/gb-2001-2-7-research0024.txt
    ./technical/biomed/gb-2001-2-7-research0025.txt
    ./technical/biomed/gb-2001-2-8-research0027.txt
    ./technical/biomed/gb-2001-2-8-research0030.txt
    ./technical/biomed/gb-2001-2-8-research0031.txt
    ./technical/biomed/gb-2001-2-8-research0032.txt
    ./technical/biomed/gb-2001-2-9-research0035.txt
    ./technical/biomed/gb-2001-2-9-research0037.txt
    ./technical/biomed/gb-2001-3-1-research0001.txt
    ./technical/biomed/gb-2001-3-1-research0004.txt
    ./technical/biomed/gb-2001-3-1-research0005.txt
    ./technical/biomed/gb-2002-3-10-research0052.txt
    ./technical/biomed/gb-2002-3-10-research0053.txt
    ./technical/biomed/gb-2002-3-10-research0054.txt
    ./technical/biomed/gb-2002-3-10-research0055.txt
    ./technical/biomed/gb-2002-3-10-research0056.txt
    ./technical/biomed/gb-2002-3-11-research0059.txt
    ./technical/biomed/gb-2002-3-11-research0060.txt
    ./technical/biomed/gb-2002-3-11-research0061.txt
    ./technical/biomed/gb-2002-3-11-research0062.txt
    ./technical/biomed/gb-2002-3-11-research0065.txt
    ./technical/biomed/gb-2002-3-12-research0071.txt
    ./technical/biomed/gb-2002-3-12-research0072.txt
    ./technical/biomed/gb-2002-3-12-research0075.txt
    ./technical/biomed/gb-2002-3-12-research0077.txt
    ./technical/biomed/gb-2002-3-12-research0078.txt
    ./technical/biomed/gb-2002-3-12-research0079.txt
    ./technical/biomed/gb-2002-3-12-research0080.txt
    ./technical/biomed/gb-2002-3-12-research0081.txt
    ./technical/biomed/gb-2002-3-12-research0082.txt
    ./technical/biomed/gb-2002-3-12-research0083.txt
    ./technical/biomed/gb-2002-3-12-research0085.txt
    ./technical/biomed/gb-2002-3-12-research0086.txt
    ./technical/biomed/gb-2002-3-12-research0087.txt
    ./technical/biomed/gb-2002-3-12-research0088.txt
    ./technical/biomed/gb-2002-3-2-research0008.txt
    ./technical/biomed/gb-2002-3-2-research0009.txt
    ./technical/biomed/gb-2002-3-3-research0011.txt
    ./technical/biomed/gb-2002-3-3-research0012.txt
    ./technical/biomed/gb-2002-3-4-research0018.txt
    ./technical/biomed/gb-2002-3-4-research0019.txt
    ./technical/biomed/gb-2002-3-5-research0020.txt
    ./technical/biomed/gb-2002-3-5-research0021.txt
    ./technical/biomed/gb-2002-3-5-research0022.txt
    ./technical/biomed/gb-2002-3-5-research0023.txt
    ./technical/biomed/gb-2002-3-5-research0024.txt
    ./technical/biomed/gb-2002-3-5-research0025.txt
    ./technical/biomed/gb-2002-3-6-research0029.txt
    ./technical/biomed/gb-2002-3-6-software0001.txt
    ./technical/biomed/gb-2002-3-7-research0032.txt
    ./technical/biomed/gb-2002-3-7-research0035.txt
    ./technical/biomed/gb-2002-3-7-research0036.txt
    ./technical/biomed/gb-2002-3-7-research0037.txt
    ./technical/biomed/gb-2002-3-8-research0038.txt
    ./technical/biomed/gb-2002-3-8-research0039.txt
    ./technical/biomed/gb-2002-3-8-research0040.txt
    ./technical/biomed/gb-2002-3-9-research0043.txt
    ./technical/biomed/gb-2002-3-9-research0044.txt
    ./technical/biomed/gb-2002-3-9-research0045.txt
    ./technical/biomed/gb-2002-3-9-research0046.txt
    ./technical/biomed/gb-2002-3-9-research0048.txt
    ./technical/biomed/gb-2002-3-9-research0049.txt
    ./technical/biomed/gb-2002-3-9-research0051.txt
    ./technical/biomed/gb-2002-4-1-r1.txt
    ./technical/biomed/gb-2002-4-1-r2.txt
    ./technical/biomed/gb-2003-4-1-r5.txt
    ./technical/biomed/gb-2003-4-1-r7.txt
    ./technical/biomed/gb-2003-4-2-r11.txt
    ./technical/biomed/gb-2003-4-2-r14.txt
    ./technical/biomed/gb-2003-4-2-r16.txt
    ./technical/biomed/gb-2003-4-2-r8.txt
    ./technical/biomed/gb-2003-4-2-r9.txt
    ./technical/biomed/gb-2003-4-3-r17.txt
    ./technical/biomed/gb-2003-4-3-r18.txt
    ./technical/biomed/gb-2003-4-3-r20.txt
    ./technical/biomed/gb-2003-4-4-r24.txt
    ./technical/biomed/gb-2003-4-4-r26.txt
    ./technical/biomed/gb-2003-4-4-r28.txt
    ./technical/biomed/gb-2003-4-5-r30.txt
    ./technical/biomed/gb-2003-4-5-r32.txt
    ./technical/biomed/gb-2003-4-5-r34.txt
    ./technical/biomed/gb-2003-4-6-r37.txt
    ./technical/biomed/gb-2003-4-6-r39.txt
    ./technical/biomed/gb-2003-4-6-r41.txt
    ./technical/biomed/gb-2003-4-7-r42.txt
    ./technical/biomed/gb-2003-4-7-r43.txt
    ./technical/biomed/gb-2003-4-7-r46.txt
    ./technical/biomed/gb-2003-4-8-r50.txt
    ./technical/biomed/gb-2003-4-8-r51.txt
    ./technical/biomed/gb-2003-4-9-r57.txt
    ./technical/biomed/gb-2003-4-9-r58.txt
    ./technical/biomed/gb-2003-4-9-r60.txt
    ./technical/biomed/rr166.txt
    ./technical/biomed/rr167.txt
    ./technical/biomed/rr171.txt
    ./technical/biomed/rr172.txt
    ./technical/biomed/rr191.txt
    ./technical/biomed/rr196.txt
    ./technical/biomed/rr37.txt
    ./technical/biomed/rr73.txt
    ./technical/biomed/rr74.txt
    ```

    Here is a basic example of using it to find some paths. In the first line, in both lines, BIOMED is in all capital letters but the second command containing `-i` is the only command the produced results because capitalization is ignored

    # Example 2
    ```
    [cs15lfa22nx@ieng6-202]:Lab:527$ grep -o "studies" technical/biomed/rr74.txt | wc
      7       7      56
    [cs15lfa22nx@ieng6-202]:Lab:528$ grep -oi "studies" technical/biomed/rr74.txt | wc
      8       8      64 
    ```

    Recall that `-o` produces words that only contain the searched string as opposed to entire lines. When paired together with `-i`, we are able to find all instances of the searched string in a text. Here, we can see that the word "studies" was shown to be written 7 times in the first command. This is technically true because S and s are two different characters. However if one wanted to know how many times the word "studies" was written in a text, then this is inaccurate. By ignoring capitilization, we get the true number of times the word has appeared in the text.

    ## Example 3:

    ```
    [cs15lfa22nx@ieng6-202]:Lab:532$ grep -o "Studies" technical/biomed/rr74.txt > Studies-results.txt
    [cs15lfa22nx@ieng6-202]:Lab:533$ grep -o "studies" technical/biomed/rr74.txt > studies-results.txt
    [cs15lfa22nx@ieng6-202]:Lab:534$ cat Studies-results.txt studies-results.txt
    Studies
    studies
    studies
    studies
    studies
    studies
    studies
    studies
    [cs15lfa22nx@ieng6-202]:Lab:535$ grep -oi "studies" technical/biomed/rr74.txt > all-studies-results.txt
    [cs15lfa22nx@ieng6-202]:Lab:536$ cat all-studies-results.txt
    studies
    studies
    Studies
    studies
    studies
    studies
    studies
    studies
    ```

    Here we see two alternate ways of arriving to a similar result. In the first set of commands, I had to manually enter different ways that "studies" could be capitalized. I also had to make two separate `.txt` files in order to store to keep track of their instances, and then I had to use the `cat` command with both files in order to display the results. This is extremely time consuming especially when considering that there are many other ways that the word "studies" could be capitalized due to typos (sTudies, stUdies, etc). Instead of thinking of every possible way a string could be spelled, it's much more efficient to use the `-i` option which also gives us the benefit of telling us the order in which the words were used.

    ---

* `-n`

    The `-n` command is an extension of the usual command except it displays the line number the the reults is found in.

    ## Example 1:

    ```
    [cs15lfa22nx@ieng6-201]:skill-demo1:510$ grep -n "studies" ./technical/biomed/rr74.txt
  10:        circulation, and previous studies using NOS inhibitors [ 1,
  15:        These discrepancies have been addressed in recent studies
  245:        studies of 4 weeks of hypoxia in mature animals [ 9]. The
  320:        [ 25, 26, 27]. Additionally, recent studies also suggest
  350:        species and tissue specific. Previous studies of NOS
  384:        previous studies, the plasma NO metabolite content in the
  410:        considering studies using NOS-deficient mice. The present
  ```
  Here is a basic use-case of the `n` command. Here it is used to find all instances that the word "studies" ws used. This is helpful when parsing through a file for specific words and knowing exactly where to find those words.

  ## Example 2:

  ```
  [cs15lfa22nx@ieng6-201]:skill-demo1:511$ grep -in "studies" ./technical/biomed/rr74.txt
  10:        circulation, and previous studies using NOS inhibitors [ 1,
  15:        These discrepancies have been addressed in recent studies
  24:        vascular tone. Studies using knockout mice for each of
  245:        studies of 4 weeks of hypoxia in mature animals [ 9]. The
  320:        [ 25, 26, 27]. Additionally, recent studies also suggest
  350:        species and tissue specific. Previous studies of NOS
  384:        previous studies, the plasma NO metabolite content in the
  410:        considering studies using NOS-deficient mice. The present
  ```
  Recall that the `-i` command ignores the capitilization of the argument. In this example, you can see how pairing both the `-i` and `-n` commands will results in all instances of a word being written regardless of capitilization. This is even more helpful than the previous example as you can see how often a word is used regardless of context.

  ## Example 3:

  ```
  [cs15lfa22nx@ieng6-201]:skill-demo1:514$ grep -in "laws" ./technical/*/*.txt                     
  ./technical/911report/chapter-12.txt:761:                not being held under a particular country's criminal laws. Countries such as
  ./technical/911report/chapter-12.txt:776:                    for those cases in which the usual laws of war did not apply. Its minimum
  ./technical/911report/chapter-12.txt:812:                laws and an international legal regime with universal jurisdiction to enable the
  ./technical/911report/chapter-12.txt:957:                laws-that is, aspects of those laws not specifically aimed at protecting against
  ./technical/911report/chapter-12.txt:1223:                Security Act followed. These laws required the development of strategic plans to
  ./technical/911report/chapter-12.txt:1343:                the immigration laws as a tool in its counterterrorism effort. Even without the
  ./technical/911report/chapter-12.txt:1371:                America's surveillance laws to reflect technological developments in a digital age.
  ./technical/911report/chapter-13.1.txt:904:                different laws and rules, to the job of the CIA's operations officers abroad.
  ./technical/911report/chapter-13.5.txt:2564:                Islam and in violation of Afghanistan's laws and the regime's tenets. Wendy
  ./technical/911report/chapter-3.txt:430:                evidence, and information-sharing conflicts resulted. New laws in 1996 authorized
  ./technical/911report/chapter-3.txt:440:                examine how immigration laws could be brought to bear on terrorism. For instance, it
  ./technical/911report/chapter-3.txt:451:                immigration laws, and an inspector general's report recommending that the Border
  ./technical/911report/chapter-3.txt:591:                agency did not consider such items to be menacing, (2) most local laws did not
  ./technical/911report/chapter-3.txt:737:                targeting persons in the United States and possibly violating laws that governed
  ./technical/911report/chapter-3.txt:1231:                faithful execution of laws. For the story of 9/11, the significance of the
  ./technical/911report/chapter-3.txt:1483:                traditional review of the administration of programs and the implementation of laws
  ./technical/911report/chapter-3.txt:2661:                had been limited by their abilities and "by our beliefs and laws we have to
  ./technical/911report/chapter-6.txt:597:                attention to America's porous borders and the weak enforcement of immigration laws.
  ./technical/biomed/1471-2105-1-1.txt:36:        is based on fundamental physicochemical laws and
  ./technical/biomed/1471-2180-2-1.txt:413:        made the laws of mechanics governing the behavior of
  ./technical/biomed/1471-2202-3-1.txt:917:          interferometry and obey the same laws [ 60 ] . For
  ./technical/biomed/1471-2202-3-7.txt:312:        limits. First, the laws of probability predict that there
  ./technical/biomed/1472-6831-3-1.txt:414:          flaws than a pressing and sintering technique as the one
  ./technical/biomed/1472-6831-3-1.txt:418:          possibility that flaws are induced when copings are
  ./technical/biomed/1472-6831-3-1.txt:419:          pressed and that these flaws may not heal completely
  ./technical/biomed/1472-6831-3-1.txt:423:          From the above argumentation, flaws may very well be
  ./technical/biomed/1472-6831-3-1.txt:431:          flaws introduced in Denzir copings are smaller or bigger
  ./technical/biomed/1472-6947-1-6.txt:447:        the quantitative effects of study design flaws on the
  ./technical/biomed/1472-6947-2-7.txt:526:          important barrier. For example, the Stark laws make
  ./technical/biomed/1472-6947-2-7.txt:551:          and security of health information. Today's laws
  ./technical/biomed/1472-6947-2-7.txt:564:          needed in this domain to develop laws and regulation that
  ./technical/biomed/1472-6963-3-14.txt:235:          ordinary common sense claims to the laws of physics - as
  ./technical/biomed/1472-6963-3-14.txt:277:          the web, e.g., laws of nature like "E=mc 2" and laws of
  ./technical/biomed/1472-6963-3-14.txt:314:          kind called logical laws. [ 12 ]
  ./technical/biomed/cc105.txt:211:        by enacting mandatory request laws have had minimal impact
  ./technical/biomed/gb-2002-3-3-research0011.txt:190:          flaws on the microarray or experimental error, an
  ./technical/biomed/gb-2002-3-8-research0040.txt:60:        laws in biology and discuss several models that aim to
  ./technical/biomed/gb-2002-3-8-research0040.txt:372:          processes to power laws [ 34, 35, 36, 37].
  ./technical/plos/journal.pbio.0020150.txt:88:        basis of such a scan would likely lead straight to a lawsuit, with experts debating whether
  ./technical/plos/journal.pbio.0020164.txt:48:        hope that fundamental laws might be recognized (Fox Keller 2002). This strategy works well
  ./technical/plos/journal.pbio.0020164.txt:53:        discern fundamental laws in them. To do so would be like expecting to discern the
  ./technical/plos/journal.pbio.0020164.txt:54:        fundamental laws of electromagnetism in the output of a personal computer.
  ./technical/plos/journal.pbio.0020214.txt:129:        at authors' Web pages, and last but not least, colleagues abroad who break copyright laws
  ./technical/plos/journal.pbio.0020262.txt:35:        Boruwlawski, last of the court dwarfs, who enchanted European royalty, married a beautiful
  ./technical/plos/journal.pbio.0020307.txt:13:        evolution) reported to date (Yang and Bielawski 2000). In particular, rates of
  ./technical/plos/journal.pbio.0020419.txt:85:        Chargaff's Laws, and means to make point mutations from which it could be determined how
  ./technical/plos/journal.pbio.0020440.txt:66:        3/4 —and more generally, why quarter-power scaling laws should be so
  ./technical/plos/journal.pbio.0020440.txt:97:        would have more blood than their bodies could contain, that biological scaling laws were
  ./technical/plos/pmed.0010039.txt:11:        goals. What are the flaws in the United States health system that prevent Americans from
  ./technical/plos/pmed.0010039.txt:86:        Flaws in Funding and Allocation
  ./technical/plos/pmed.0010039.txt:162:        address the deteriorating status of our health care system. Correcting the flaws in
  ./technical/plos/pmed.0020009.txt:150:        the public's interest. This value is even codified in the laws granting these institutions
  ./technical/plos/pmed.0020047.txt:33:        folly, and should fund it directly, as in the past. Meanwhile, laws that encourage
  ./technical/plos/pmed.0020071.txt:52:        laws must provide for minimum substantive and procedural protections that protect mentally
  ./technical/plos/pmed.0020071.txt:54:        found that civil commitment laws in Uruguay and Mexico allow commitment upon medical
  ./technical/plos/pmed.0020071.txt:57:        These laws do not require a right to counsel or a periodic review of commitment, as
  ./technical/plos/pmed.0020098.txt:22:        flaws. They do not take family history of premature coronary artery disease into account;
  ./technical/plos/pmed.0020098.txt:86:        conventional screening tools [18,19], but the first of these has serious flaws (such as a
  ./technical/plos/pmed.0020208.txt:19:        led to lawsuits by at least two of the whistleblowers [2,3]. The picture that emerged from
  ./technical/plos/pmed.0020209.txt:48:            algorithm. He filed a civil rights lawsuit against the Pennsylvania Office of the
  ./technical/plos/pmed.0020209.txt:194:            lawsuit “to preserve my job and my right to speak out.” His employer, he said, took him
  ./technical/plos/pmed.0020246.txt:271:            laws against discrimination were suggested by 11% (Table 6).
  ./technical/plos/pmed.0020247.txt:119:        condom, or request an HIV test. If a husband should die, the wife's in-laws may seize her
  ```

  Here, the command is being used to parse through several `.txt` files through the use of the `*` command. Again, by using both the `-i` and `n` command, we can see every instance that the string "laws" shows up. What is nice about this use however is that the terminal displays what file the string is found in as well as the line. This is helpful when trying to find a piece of data over multiple files without having to check each individual file one at a time. 