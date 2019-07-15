# Sample script for deleting twitter

run in your tweets page using dev-tool.

```js
function deleteTweets() {
    let tl = $("#timeline .tweet .js-actionDelete button")
    tl.each(i => {
        tl[i].click();
        $("#delete-tweet-dialog button.delete-action").first().click();
    })
    $(window).scrollTop(0);
    $(window).scrollTop($("#timeline").height());
}
intervalId = setInterval(() => {
    let tl = $("#timeline .tweet .js-actionDelete button")
    if (tl && tl.length > 10) {
        deleteTweets();
    }else {
        clearInterval(intervalId);
    }
}, 3000)

```
