## Setting up

[Level 0](https://overthewire.org/wargames/bandit/bandit0.html)

- Using SSH to connect to `bandit.labs.overthewire.org` on port `2220` using username: _bandit0_ and password: _bandit0_

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

## Solution

[Level 0 -> 1](https://overthewire.org/wargames/bandit/bandit1.html)

- `pwd: boJ9jbbUNNfktd78OOpsqOltutMc3MY1`

[Level 1 -> 2](https://overthewire.org/wargames/bandit/bandit2.html)

- cat ./-
- `pwd: CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9`

[Level 2 -> 3](https://overthewire.org/wargames/bandit/bandit3.html)

- `pwd: UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK`

[Level 3 -> 4](https://overthewire.org/wargames/bandit/bandit4.html)

- `pwd: pIwrPrtPN36QITSp3EQaw936yaFoFgAB`

[Level 4 -> 5](https://overthewire.org/wargames/bandit/bandit5.html)

- Find human readable file with this: find -type f | xargs file | grep text
  (xargs file will run the file command on each of the lines from the piped input.)
- `pwd: koReBOKuIDDepwhWk7jZC0RTdopnAYKh`

[Level 5 -> 6](https://overthewire.org/wargames/bandit/bandit6.html)

- find -readable -size 1033c
- `pwd: DXjZPULLxYr17uwoI01bNLQbtFemEgo7`

[Level 6 -> 7](https://overthewire.org/wargames/bandit/bandit7.html)

- cat `find -size 33c -group bandit6 -user bandit7 2>/dev/null`
- (`2>/dev/null` redirects all standard errors like `No such file or directory` and `Permission denied` to `/dev/null` where `null` acts as a special device which discards all information written to it. Thus we only get the one required file as output which I sent as input to cat to see its contents.)
- `pwd: HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs`

[Level 7 -> 8](https://overthewire.org/wargames/bandit/bandit8.html)

- cat data.txt | grep millionth
- `pwd: cvX2JJa4CFALtqS87jk27qwqGhBM9plV`

[Level 8 -> 9](https://overthewire.org/wargames/bandit/bandit9.html)

- cat data.txt | sort | uniq -u
- (https://kongwenbin.wordpress.com/2016/08/17/overthewire-bandit-level-8-to-level-9/)
- `pwd: UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR`

[Level 9 -> 10](https://overthewire.org/wargames/bandit/bandit10.html)

- strings data.txt | grep "="
- (https://kongwenbin.wordpress.com/2016/08/20/overthewire-bandit-level-9-to-level-10/)
- `pwd: truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk`

[Level 10 -> 11](https://overthewire.org/wargames/bandit/bandit11.html)

- base64 -d data.txt
- `pwd: IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR`

[Level 11 -> 12](https://overthewire.org/wargames/bandit/bandit12.html)

- cat data.txt | tr ‘n-za-mN-ZA-M’ ‘a-zA-Z’
- (https://www.chmag.in/articles/momsguide/decoding-rot-using-the-echo-and-tr-commands-in-your-linux-terminal/)
- `pwd: 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu`

[Level 12 -> 13](https://overthewire.org/wargames/bandit/bandit13.html)

```bash
mkdir /tmp/filename
cp data.txt /tmp/filename
cd /tmp/filename
xxd -r data.txt > newfilename (reverse hashdump using xxd)
file newfilename (check type of file)

gzip: mv newfilename newfilename.gz | gzip -d newfilename.gz
bzip2: mv newfilename newfilename.bz2 | bzip2 -d newfilename.bz2
POSIX tar: mv newfilename newfilename.tar | tar xvf newfilename.tar
```

- Until see ASCII text.

- `pwd: 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL`

[Level 13 -> 14](https://overthewire.org/wargames/bandit/bandit14.html)
