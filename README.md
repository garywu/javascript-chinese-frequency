# javascript-chinese-frequency
JavaScript implementation of the ChineseFrequency object


## WALKTHROUGH


### ADDING LIBRARIES

+ Add the following scripts to your HTML document.

```html
  <script src="IdxHanyuPinyinMicro.js"></script>
  <script src="IdxExtraPinyin.js"></script>
  <script src="ChineseFrequency.js"></script>
```

### DEMO

+ Add this demo between `<script type="text/javascript">` and `</script>` tags.

```javascript

    // sample text
    var str = '隨著劇情的推進，雲高爾和曼聯之間的主帥大戲正逐步推向高潮。荷蘭人一方面將精'
      + '力投入到國家隊的世界盃備戰，另外一方面也不忘適時關注一下自己執教生涯的前途。據《每'
      + '日星報》消息，雲高爾已經同意入主曼聯，確認的消息將會在下週正式公佈。';

    // builds new object
    var c = new ChineseFrequency();
    console.log(c);
```

```javascript

    // getters and setters
    c.setInput(str);
    console.log('INPUT-STRING:' + c.getInput());
```


```javascript

    // convenience method to detect list building success
    console.log('HAS-LIST:' + c.hasList());
```

```javascript

    // count summary using toString() method
    console.log('COUNT-SUMMARY-OBJECT-TOSTRING:' + c);

    // count summary
    console.log('COUNT-SUMMARY-METHOD:' + c.getCountSummary());
```

```javascript

    // input string length
    console.log('STRING-LENGTH:' + str.length);
```

```javascript

    // total number of characters in input string
    console.log('TOTAL-INPUT:' + c.getTotalInput());
```

```javascript

    // total number of characters removed
    console.log('TOTAL-REMOVED:' + c.getTotalRemoved());
```

```javascript

    // total number of Chinese characters remaining
    console.log('TOTAL-HANZI:' + c.getTotalHanzi());
```

```javascript

    // total number of unique Chinese characters
    console.log('TOTAL-UNIQUE:' + c.getTotalUnique());
```

```javascript

    // total number of characters processed
    console.log('TOTAL-PROCESSED:' + c.getTotalProcessed());
```

### LISTS

```javascript

    // csv list
    console.log('CSV-LIST:\r\n' + c.getCsvList());
```

+ Returns a CSV list

```
CSV-LIST:
hz,py,freq
的,de5,5
高,gao1,3
一,yi1,3
正,zheng4,2
息,xi2,2
爾,er3,2
曼,man4,2
聯,lian2,2
主,zhu3,2
推,tui1,2
雲,yun2,2
方,fang1,2
面,mian4,2
將,jiang1,2
入,ru4,2
下,xia4,2
消,xiao1,2
界,jie4,1
戲,xi4,1
劇,ju4,1
逐,zhu2,1
步,bu4,1
向,xiang4,1
潮,chao2,1
荷,he2,1
蘭,lan2,1
人,ren2,1
和,he2,1
進,jin4,1
情,qing2,1
之,zhi1,1
精,jing1,1
力,li4,1
投,tou2,1
間,jian1,1
到,dao4,1
國,guo2,1
家,jia1,1
隊,dui4,1
世,shi4,1
著,zhe5,1
盃,bei1,1
備,bei4,1
戰,zhan4,1
另,ling4,1
外,wai4,1
也,ye3,1
不,bu4,1
忘,wang4,1
適,shi4,1
時,shi2,1
關,guan1,1
注,zhu4,1
隨,sui2,1
自,zi4,1
己,ji3,1
執,zhi2,1
教,jiao4,1
生,sheng1,1
涯,ya2,1
前,qian2,1
途,tu2,1
據,ju4,1
每,mei3,1
日,ri4,1
星,xing1,1
報,bao4,1
帥,shuai4,1
大,da4,1
已,yi3,1
經,jing1,1
同,tong2,1
意,yi4,1
確,que4,1
認,ren4,1
會,hui4,1
在,zai4,1
週,zhou1,1
式,shi4,1
公,gong1,1
佈,bu4,1
```

```javascript

    // data range
    console.log('DATA RANGE: arrays of arrays');
    console.log(c.getDataRange());
```

+ Returns a data range (an array of arrays)

```
[["的", "de5", 5], ["高", "gao1", 3], ["一", "yi1", 3], ["推", "tui1", 2], ["雲", "yun2", 2], ["爾", "er3", 2], ["曼", "man4", 2], ["聯", "lian2", 2], ["主", "zhu3", 2], ["正", "zheng4", 2], ["方", "fang1", 2], ["面", "mian4", 2], ["將", "jiang1", 2], ["入", "ru4", 2], ["下", "xia4", 2], ["消", "xiao1", 2], ["息", "xi2", 2], ["隨", "sui2", 1], ["著", "zhe5", 1], ["劇", "ju4", 1], ["情", "qing2", 1], ["進", "jin4", 1], ["和", "he2", 1], ["之", "zhi1", 1], ["間", "jian1", 1], ["帥", "shuai4", 1], ["大", "da4", 1], ["戲", "xi4", 1], ["逐", "zhu2", 1], ["步", "bu4", 1], ["向", "xiang4", 1], ["潮", "chao2", 1], ["荷", "he2", 1], ["蘭", "lan2", 1], ["人", "ren2", 1], ["精", "jing1", 1], ["力", "li4", 1], ["投", "tou2", 1], ["到", "dao4", 1], ["國", "guo2", 1], ["家", "jia1", 1], ["隊", "dui4", 1], ["世", "shi4", 1], ["界", "jie4", 1], ["盃", "bei1", 1], ["備", "bei4", 1], ["戰", "zhan4", 1], ["另", "ling4", 1], ["外", "wai4", 1], ["也", "ye3", 1], ["不", "bu4", 1], ["忘", "wang4", 1], ["適", "shi4", 1], ["時", "shi2", 1], ["關", "guan1", 1], ["注", "zhu4", 1], ["自", "zi4", 1], ["己", "ji3", 1], ["執", "zhi2", 1], ["教", "jiao4", 1], ["生", "sheng1", 1], ["涯", "ya2", 1], ["前", "qian2", 1], ["途", "tu2", 1], ["據", "ju4", 1], ["每", "mei3", 1], ["日", "ri4", 1], ["星", "xing1", 1], ["報", "bao4", 1], ["已", "yi3", 1], ["經", "jing1", 1], ["同", "tong2", 1], ["意", "yi4", 1], ["確", "que4", 1], ["認", "ren4", 1], ["會", "hui4", 1], ["在", "zai4", 1], ["週", "zhou1", 1], ["式", "shi4", 1], ["公", "gong1", 1], ["佈", "bu4", 1]]
```