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

    c.setInput(str);

    console.log('INPUT-STRING:' + c.getInput());

    // convenience method to detect list building success
    console.log('HAS-LIST:' + c.hasList());

    // count summary using toString() method
    console.log('COUNT-SUMMARY-OBJECT-TOSTRING:' + c);

    // count summary
    console.log('COUNT-SUMMARY-METHOD:' + c.getCountSummary());

    console.log('STRING-LENGTH:' + str.length); // input string length

    // STATS

    // total number of characters in input string
    console.log('TOTAL-INPUT:' + c.getTotalInput());

    // total number of characters removed
    console.log('TOTAL-REMOVED:' + c.getTotalRemoved());

    // total number of Chinese characters remaining
    console.log('TOTAL-HANZI:' + c.getTotalHanzi());

    // total number of unique Chinese characters
    console.log('TOTAL-UNIQUE:' + c.getTotalUnique());

    // total number of characters processed
    console.log('TOTAL-PROCESSED:' + c.getTotalProcessed());

    // csv list
    console.log('CSV-LIST:\r\n' + c.getCsvList());

    console.log('DATA RANGE: arrays of arrays');
    console.log(c.getDataRange()); // data range
```