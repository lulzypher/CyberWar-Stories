---
Crafted by [Genie](https://marketplace.visualstudio.com/items?itemName=genieai.chatgpt-vscode)

---

## You

Im trying to work with 
https://github.com/sporkexec/rubberhose
but I dont understand it that well.

How would I create a keymap and run this github with the info given below?

SALTS:
insurance.aes256 DE 18 1B 73 EF F3 5E 39 DA
wlinsurance-20130815-A.aes256 0F 0B DA 00 F0 35 9A 0F C8
wlinsurance-20130815-B.aes256 AB C2 04 75 6B AB 85 BE 30
wlinsurance-20130815-C.aes256 73 6B 46 4C 2F 84 9A C2 A4

US Kerry [1]- 4bb96075acadc3d80b5ac872874c3037a386f4f595fe99e687439aabd0219809
UK FCO [2]- f33a6de5c627e3270ed3e02f62cd0c857467a780cf6123d2172d80d02a072f74
EC [3]- eae5c9b064ed649ba468f0800abf8b56ae5cfe355b93b1ce90a1b92a48a9ab72

sha256sum 2016-11-07_WL-Insurance_US.aes256 ab786b76a195cacde2d94506ca512ee950340f1404244312778144f67d4c8002
sha256sum 2016-11-07_WL-Insurance_UK.aes256 655821253135f8eabff54ec62c7f243a27d1d0b7037dc210f59267c43279a340
sha256sum 2016-11-07_WL-Insurance_EC.aes256 b231ccef70338a857e48984f0fd73ea920eff70ab6b593548b0adcbd1423b995

wlinsurance-20130815-A.aes256 [5],[6]
6688fffa9b39320e11b941f0004a3a76d49c7fb52434dab4d7d881dc2a2d7e02

wlinsurance-20130815-B.aes256 [5], [7]
3dcf2dda8fb24559935919fab9e5d7906c3b28476ffa0c5bb9c1d30fcb56e7a4

wlinsurance-20130815-C.aes256 [5], [8]
913a6ff8eca2b20d9d2aab594186346b6089c0fb9db12f64413643a8acadcfe3

insurance.aes256 [9], [10]
cce54d3a8af370213d23fcbfe8cddc8619a0734c

## Genie

To create a keymap and run `rubberhose` with the given salts and keys, follow these steps:

1. First, clone the Github repository using the command:

   ```
   git clone https://github.com/sporkexec/rubberhose.git
   ```

2. Navigate to the cloned directory and open the `keymap.py` file using a text editor.

3. In the `keymap.py` file, create a new dictionary containing the salts and keys as shown below:

   ```python
   keymap = {
       "insurance.aes256": ["DE181B73EFF35E39DA", "cce54d3a8af370213d23fcbfe8cddc8619a0734c"],
       "wlinsurance-20130815-A.aes256": ["0F0BDA00F0359A0FC8", "6688fffa9b39320e11b941f0004a3a76d49c7fb52434dab4d7d881dc2a2d7e02"],
       "wlinsurance-20130815-B.aes256": ["ABC204756BAB85BE30", "3dcf2dda8fb24559935919fab9e5d7906c3b28476ffa0c5bb9c1d30fcb56e7a4"],
       "wlinsurance-20130815-C.aes256": ["736B464C2F849AC2A4", "913a6ff8eca2b20d9d2aab594186346b6089c0fb9db12f64413643a8acadcfe3"]
   }
   ```

   Here, the dictionary key represents the filename and the dictionary value represents the salt and key for that file.

4. Save the `keymap.py` file and navigate to the `rubberhose` directory in the terminal.

5. To list the possible commands and options for using `rubberhose`, run the following command:

   ```
   python rubberhose.py --help
   ```

6. To extract a file with a given salt, run the following command (replace `<filename>` with the name of the file you want to extract):

   ```
   python rubberhose.py -d <filename>
   ```

7. To inject a file with a given salt, run the following command (replace `<filename>` with the name of the file you want to inject):

   ```
   python rubberhose.py -i <filename>
   ```

That's it! You should now be able to use `rubberhose` with your keymap and extract or inject files with the given salts and keys.