# Sample script for deleting twitter

いまのところリツイートには対応していない。

```js
// Mar 2022

// login and open your profile page.
// open devtool and paste codes below.

function deleteTopTweet(){
    document.querySelectorAll('[aria-haspopup="menu"]')[1].click();
    let me = document.querySelectorAll('[aria-haspopup="menu"]')[1];
    let mi0 = document.querySelectorAll('[role="menuitem"]')[0];
    if (mi0.querySelector('span').innerText == '削除' ) {
        mi0.click();
        document.querySelectorAll('[role="button"][data-testid="confirmationSheetConfirm"]')[0].click();
    }
}

function sleep(ms) {
    return new Promise(resolve => setTimeout(resolve, ms));
}

async function deleteMultipleTweets(loop) {
    for (let i = 0; i < loop; i++) {
        deleteTopTweet();
        console.log(`[${i}]deleted.`);
        await sleep(500);
    }
    console.log('Done');
}

deleteMultipleTweets(100);

```
