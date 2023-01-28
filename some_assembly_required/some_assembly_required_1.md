# some assembly required 1
picoCTF2021 Web Exploitation
## Description
http://mercury.picoctf.net:40226/index.html
## Hints
none
## Walkthrough
1-open the url and click ctr+shift+i to inspect
```html

	<h4>Enter flag:</h4>
	<input type="text" id="input">
	<button onclick="onButtonPress()">Submit</button>
	<p id="result"></p>
```
2-go to the debugger to view the javascript code in the G82XCw5CX3.js file
```javascript
const _0x402c=['value','2wfTpTR','instantiate','275341bEPcme','innerHTML','1195047NznhZg','1qfevql','input','1699808QuoWhA','Correct!','check_flag','Incorrect!','./JIFxzHyW8W','23SMpAuA','802698XOMSrr','charCodeAt','474547vVoGDO','getElementById','instance','copy_char','43591XxcWUl','504454llVtzW','arrayBuffer','2NIQmVj','result'];const _0x4e0e=function(_0x553839,_0x53c021){_0x553839=_0x553839-0x1d6;let _0x402c6f=_0x402c[_0x553839];return _0x402c6f;};(function(_0x76dd13,_0x3dfcae){const _0x371ac6=_0x4e0e;while(!![]){try{const _0x478583=-parseInt(_0x371ac6(0x1eb))+parseInt(_0x371ac6(0x1ed))+-parseInt(_0x371ac6(0x1db))*-parseInt(_0x371ac6(0x1d9))+-parseInt(_0x371ac6(0x1e2))*-parseInt(_0x371ac6(0x1e3))+-parseInt(_0x371ac6(0x1de))*parseInt(_0x371ac6(0x1e0))+parseInt(_0x371ac6(0x1d8))*parseInt(_0x371ac6(0x1ea))+-parseInt(_0x371ac6(0x1e5));if(_0x478583===_0x3dfcae)break;else _0x76dd13['push'](_0x76dd13['shift']());}catch(_0x41d31a){_0x76dd13['push'](_0x76dd13['shift']());}}}(_0x402c,0x994c3));let exports;(async()=>{const _0x48c3be=_0x4e0e;let _0x5f0229=await fetch(_0x48c3be(0x1e9)),_0x1d99e9=await WebAssembly[_0x48c3be(0x1df)](await _0x5f0229[_0x48c3be(0x1da)]()),_0x1f8628=_0x1d99e9[_0x48c3be(0x1d6)];exports=_0x1f8628['exports'];})();function onButtonPress(){const _0xa80748=_0x4e0e;let _0x3761f8=document['getElementById'](_0xa80748(0x1e4))[_0xa80748(0x1dd)];for(let _0x16c626=0x0;_0x16c626<_0x3761f8['length'];_0x16c626++){exports[_0xa80748(0x1d7)](_0x3761f8[_0xa80748(0x1ec)](_0x16c626),_0x16c626);}exports['copy_char'](0x0,_0x3761f8['length']),exports[_0xa80748(0x1e7)]()==0x1?document[_0xa80748(0x1ee)](_0xa80748(0x1dc))[_0xa80748(0x1e1)]=_0xa80748(0x1e6):document[_0xa80748(0x1ee)](_0xa80748(0x1dc))[_0xa80748(0x1e1)]=_0xa80748(0x1e8);}
```
this looks loke obfuscated javascript code, take it to your IDE and format it to be more reabable
```javascript
const _0x402c = [
  "value",
  "2wfTpTR",
  "instantiate",
  "275341bEPcme",
  "innerHTML",
  "1195047NznhZg",
  "1qfevql",
  "input",
  "1699808QuoWhA",
  "Correct!",
  "check_flag",
  "Incorrect!",
  "./JIFxzHyW8W",
  "23SMpAuA",
  "802698XOMSrr",
  "charCodeAt",
  "474547vVoGDO",
  "getElementById",
  "instance",
  "copy_char",
  "43591XxcWUl",
  "504454llVtzW",
  "arrayBuffer",
  "2NIQmVj",
  "result",
];
const _0x4e0e = function (_0x553839, _0x53c021) {
  _0x553839 = _0x553839 - 0x1d6;
  let _0x402c6f = _0x402c[_0x553839];
  return _0x402c6f;
};
(function (_0x76dd13, _0x3dfcae) {
  const _0x371ac6 = _0x4e0e;
  while (!![]) {
    try {
      const _0x478583 =
        -parseInt(_0x371ac6(0x1eb)) +
        parseInt(_0x371ac6(0x1ed)) +
        -parseInt(_0x371ac6(0x1db)) * -parseInt(_0x371ac6(0x1d9)) +
        -parseInt(_0x371ac6(0x1e2)) * -parseInt(_0x371ac6(0x1e3)) +
        -parseInt(_0x371ac6(0x1de)) * parseInt(_0x371ac6(0x1e0)) +
        parseInt(_0x371ac6(0x1d8)) * parseInt(_0x371ac6(0x1ea)) +
        -parseInt(_0x371ac6(0x1e5));
      if (_0x478583 === _0x3dfcae) break;
      else _0x76dd13["push"](_0x76dd13["shift"]());
    } catch (_0x41d31a) {
      _0x76dd13["push"](_0x76dd13["shift"]());
    }
  }
})(_0x402c, 0x994c3);
let exports;
(async () => {
  const _0x48c3be = _0x4e0e;
  let _0x5f0229 = await fetch(_0x48c3be(0x1e9)),
    _0x1d99e9 = await WebAssembly[_0x48c3be(0x1df)](
      await _0x5f0229[_0x48c3be(0x1da)]()
    ),
    _0x1f8628 = _0x1d99e9[_0x48c3be(0x1d6)];
  exports = _0x1f8628["exports"];
})();
function onButtonPress() {
  const _0xa80748 = _0x4e0e;
  let _0x3761f8 = document["getElementById"](_0xa80748(0x1e4))[
    _0xa80748(0x1dd)
  ];
  for (let _0x16c626 = 0x0; _0x16c626 < _0x3761f8["length"]; _0x16c626++) {
    exports[_0xa80748(0x1d7)](
      _0x3761f8[_0xa80748(0x1ec)](_0x16c626),
      _0x16c626
    );
  }
  exports["copy_char"](0x0, _0x3761f8["length"]),
    exports[_0xa80748(0x1e7)]() == 0x1
      ? (document[_0xa80748(0x1ee)](_0xa80748(0x1dc))[_0xa80748(0x1e1)] =
          _0xa80748(0x1e6))
      : (document[_0xa80748(0x1ee)](_0xa80748(0x1dc))[_0xa80748(0x1e1)] =
          _0xa80748(0x1e8));
}
```
by deobfuscating the code we get:
```javascript
'use strict';
const _0x402c = ["value", "2wfTpTR", "instantiate", "275341bEPcme", "innerHTML", "1195047NznhZg", "1qfevql", "input", "1699808QuoWhA", "Correct!", "check_flag", "Incorrect!", "./JIFxzHyW8W", "23SMpAuA", "802698XOMSrr", "charCodeAt", "474547vVoGDO", "getElementById", "instance", "copy_char", "43591XxcWUl", "504454llVtzW", "arrayBuffer", "2NIQmVj", "result"];
const _0x4e0e = function(url, whensCollection) {
  /** @type {number} */
  url = url - 470;
  let _0x402c6f = _0x402c[url];
  return _0x402c6f;
};
(function(data, oldPassword) {
  const toMonths = _0x4e0e;
  for (; !![];) {
    try {
      const userPsd = -parseInt(toMonths(491)) + parseInt(toMonths(493)) + -parseInt(toMonths(475)) * -parseInt(toMonths(473)) + -parseInt(toMonths(482)) * -parseInt(toMonths(483)) + -parseInt(toMonths(478)) * parseInt(toMonths(480)) + parseInt(toMonths(472)) * parseInt(toMonths(490)) + -parseInt(toMonths(485));
      if (userPsd === oldPassword) {
        break;
      } else {
        data["push"](data["shift"]());
      }
    } catch (_0x41d31a) {
      data["push"](data["shift"]());
    }
  }
})(_0x402c, 627907);
let exports;
(async() => {
  const findMiddlePosition = _0x4e0e;
  let leftBranch = await fetch(findMiddlePosition(489));
  let rightBranch = await WebAssembly[findMiddlePosition(479)](await leftBranch[findMiddlePosition(474)]());
  let module = rightBranch[findMiddlePosition(470)];
  exports = module["exports"];
})();
/**
 * @return {undefined}
 */
function onButtonPress() {
  const navigatePop = _0x4e0e;
  let params = document["getElementById"](navigatePop(484))[navigatePop(477)];
  for (let i = 0; i < params["length"]; i++) {
    exports[navigatePop(471)](params[navigatePop(492)](i), i);
  }
  exports["copy_char"](0, params["length"]);
  if (exports[navigatePop(487)]() == 1) {
    document[navigatePop(494)](navigatePop(476))[navigatePop(481)] = navigatePop(486);
  } else {
    document[navigatePop(494)](navigatePop(476))[navigatePop(481)] = navigatePop(488);
  }
}
;
```
The main part of the code is as follows:

1.It creates an async function that loads a WebAssembly module from a remote location using fetch() and WebAssembly.instantiate(), there is a file in the debugger that contains webassembly code that we will look at.

2-It assigns the exports of the WebAssembly module to a variable exports, Exports of a WebAssembly module are the functions and memory objects that are exposed by the module and can be called from the JavaScript context. 

3-It defines a function onButtonPress() that is called when a button is pressed.

4-The function takes the value of an input field, converts it to an array of characters, and passes each character to the exports.copy_char function, which is likely to be a function defined in the WebAssembly module.

5-It then calls exports.check_flag() which is likely to be another function defined in the WebAssembly module.

6-The function then compares the result of the exports.check_flag() function with the value 1, and sets the innerHTML of a element with the id "result" to "Correct!" if the values match or "Incorrect!" if they do not.

by viewing the webassem folder and the file in it we see that it contains some assembly code, and the flag is in the end of the file
```assembly
i32.load offset=12
    local.set $var5
    local.get $var4
    i32.load offset=8
    local.set $var6
    local.get $var6
    local.get $var5
    i32.store8 offset=1072
    return
  )
  (data (i32.const 1024) "picoCTF{cb688c00b5a2ede7eaedcae883735759}\00\00")
)
```

flag =>picoCTF{cb688c00b5a2ede7eaedcae883735759}

