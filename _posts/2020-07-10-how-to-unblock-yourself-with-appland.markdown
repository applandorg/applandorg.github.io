---
layout: post
title:  "How to unblock yourself with AppLand"
author: Kevin Gilpin
permalink: /blog/:year/:month/:day/:title/
thumb: /assets/img/posts/unblock-yourself-thumb.jpg
image: /assets/img/posts/unblock-yourself-illo.svg
---

I was recently answering a question on StackOverflow when I began to think about a really common problem which is evident among the questions posted on SO. The problem is that sometimes, even after reading documentation and blogs, it’s not clear how to get an open-source library to do what you want. People can struggle for hours or days on these problems. This is the fundamental gist of many, many SO questions. 

The two most common techniques that developers use to unblock their understanding are to read the docs and read the code. However, docs and code are only useful sources of “how-to” information when you already know what you are looking for. What about when the problem is that you aren’t sure where to start? In this case, an overall picture of the problem is required; one that enables the developer to see the high-level operation of the code, and then drill down into the specific areas of relevance. Once the developer’s attention is on the right areas of the code, then source code and docs help provide the last bit of understanding which is required in order to proceed.

AppLand is a powerful tool that provides visualizations to help you understand just about any code, including open source libraries. It works by auto-generating interactive depictions of the code behavior that you are trying to understand.

Here’s a general strategy that you can use to understand just about any open-source code using AppLand:

Write a program which exercises the code you want to understand.
Run your program with the AppLand client library loaded and enabled.
Start an AppLand recording, either programmatically or using the AppLand browser extension.
Exercise your app, either graphically or through its API.
Stop the recording and upload it to AppLand.
Use the AppLand scenario view to inspect the recording and understand how the application code works.



As an example, a user recently asked the Stack Overflow community [How to properly close a Net::SSH connection?](https://stackoverflow.com/questions/62643718/how-to-properly-close-a-netssh-connection). Net::SSH is a Ruby library that’s used to program the SSH protocol. This StackOverflow user wanted to go beyond the basic usage presented by the project web site, net-ssh generated documentation didn’t provide the answers.

To help answer this question, we prepared [a test program that uses the Net::SSH library](https://github.com/applandinc/land-of-applets/blob/master/how-to-properly-close-a-netssh-connection_62643718/main.rb#L16), and then recorded this program in action. The AppMap of this test program clearly shows how a Net::SSH connection proceeds through the following stages: 

1. [Configuration](https://app.land/scenarios/00087d38-6555-46e8-b713-f1c66615a742#event=6&filterShow=sql_select%2Csql_insert%2Csql_update%2Ctrivial_functions%2Cstatic_asset_requests%2Cstack_depth_less&filterShowParams=%7B%22stack_depth_less%22%3A%225%22%7D)

    ![Configuration](/images/how-to-unblock-yourself-with-appland/configuration.png)

2. [Loading host keys](https://app.land/scenarios/00087d38-6555-46e8-b713-f1c66615a742#event=6&filterShow=sql_select%2Csql_insert%2Csql_update%2Ctrivial_functions%2Cstatic_asset_requests%2Cstack_depth_less&filterShowParams=%7B%22stack_depth_less%22%3A%225%22%7D)

    ![Loading host keys](/images/how-to-unblock-yourself-with-appland/host-keys.png)

3. [Startup message](https://app.land/scenarios/00087d38-6555-46e8-b713-f1c66615a742#event=150&filterShow=sql_select%2Csql_insert%2Csql_update%2Ctrivial_functions%2Cstatic_asset_requests%2Cstack_depth_less&filterShowParams=%7B%22stack_depth_less%22%3A%225%22%7D)

    ![Startup message](/images/how-to-unblock-yourself-with-appland/startup-message.png)

4. [Authentication](https://app.land/scenarios/00087d38-6555-46e8-b713-f1c66615a742#event=1286&filterShow=sql_select%2Csql_insert%2Csql_update%2Ctrivial_functions%2Cstatic_asset_requests%2Cstack_depth_less&filterShowParams=%7B%22stack_depth_less%22%3A%225%22%7D), proceeding through auth methods None, public key, and password]

    ![Authentication](/images/how-to-unblock-yourself-with-appland/authentication.png)

5.  [Command execution](https://app.land/scenarios/00087d38-6555-46e8-b713-f1c66615a742#event=2536&filterShow=sql_select%2Csql_insert%2Csql_update%2Ctrivial_functions%2Cstatic_asset_requests%2Cstack_depth_less&filterShowParams=%7B%22stack_depth_less%22%3A%225%22%7D) (interactive)

    ![Command execution](/images/how-to-unblock-yourself-with-appland/command-execution.png)

6. [Closing the session](https://app.land/scenarios/00087d38-6555-46e8-b713-f1c66615a742#event=7254&filterShow=sql_select%2Csql_insert%2Csql_update%2Ctrivial_functions%2Cstatic_asset_requests%2Cstack_depth_less&filterShowParams=%7B%22stack_depth_less%22%3A%225%22%7D)

    ![Closing the session](/images/how-to-unblock-yourself-with-appland/closing-the-session.png)

By the way, it’s evident here the answer to the original question (how to close the connection) is to use [Net::SSH::Connection::Session#close](https://www.rubydoc.info/github/net-ssh/net-ssh/Net%2FSSH%2FConnection%2FSession:close). This method is in the documentation, but there are 5 “close” methods in the documentation, and one “do_close”, so it’s understandable why the Stack Overflow user wasn’t sure which one to use. The AppMap makes it very clear what to do!


