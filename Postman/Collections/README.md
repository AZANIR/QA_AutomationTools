<section>
    <div>
        <div class="fo fp fq fr fs">
            <div class="ab ca">
                <div class="ch bg fa fb fc fd">
                    <div>
                        <h1
                            id="cd80"
                            class="pw-post-title ft fu fv be fw fx fy fz ga gb gc gd ge gf gg gh gi gj gk gl gm gn go gp gq gr gs gt gu gv bj"
                            data-testid="storyTitle"
                            data-selectable-paragraph=""
                        >
                            Postman collection integration using Jenkins and
                            visualization using Newman reporter
                        </h1>
                    </div>
                    <figure class="lt lu lv lw lx ly lq lr paragraph-image">
                        <div class="lq lr ls">
                            <picture
                                ><img
                                    alt=""
                                    class="bg ky lz c"
                                    width="614"
                                    height="285"
                                    loading="eager"
                                    role="presentation"
                                    src="https://miro.medium.com/v2/resize:fit:614/1*9gyOFOn482a5XKULrnS1-w.png"
                            /></picture>
                        </div>
                        <figcaption
                            class="ma mb mc lq lr md me be b bf z dw"
                            data-selectable-paragraph=""
                        >
                            Source: Postman
                        </figcaption>
                    </figure>
                    <p
                        id="d835"
                        class="pw-post-body-paragraph mf mg fv mh b mi mj mk ml mm mn mo mp mq mr ms mt mu mv mw mx my mz na nb nc fo bj"
                        data-selectable-paragraph=""
                    >
                        It’s been a long time since I wrote my last article.
                        Better late than never. I am back with one more article
                        where we discuss how can we execute postman collection
                        in CLI, how to integrate postman collection to Jenkins
                        and also discuss how can we create one nicely displayed
                        HTML report with the collection results. So let’s start
                        our journey without wasting much time.
                    </p>
                    <p
                        id="0320"
                        class="pw-post-body-paragraph mf mg fv mh b mi mj mk ml mm mn mo mp mq mr ms mt mu mv mw mx my mz na nb nc fo bj"
                        data-selectable-paragraph=""
                    >
                        There are different ways to run your postman collection.
                        One way is to run the collection directly from the
                        postman UI and another way is using the Newman tool.
                    </p>
                    <p
                        id="cf1f"
                        class="pw-post-body-paragraph mf mg fv mh b mi mj mk ml mm mn mo mp mq mr ms mt mu mv mw mx my mz na nb nc fo bj"
                        data-selectable-paragraph=""
                    >
                        Newman is a command line tool to run your postman
                        collections. Newman allows user to run the postman
                        collections directly through command line interface.
                        Newman is built on Node.js. So to download the Newman,
                        users should have Node.js installed on their machine.
                        Once Node.js is installed, users can download the Newman
                        with below command.
                    </p>
                    <h1
                        id="1eb9"
                        class="nd ne fv be nf ng nh ni nj nk nl nm nn no np nq nr ns nt nu nv nw nx ny nz oa bj"
                        data-selectable-paragraph=""
                    >
                        Newman Installation
                    </h1>
                    <pre
                        class="ob oc od oe of og oh oi oj ax ok bj"
                    ><span id="a2f8" class="ol ne fv oh b hp om on l oo op" data-selectable-paragraph="">npm install -g newman</span></pre>
                    <p
                        id="4bf0"
                        class="pw-post-body-paragraph mf mg fv mh b mi mj mk ml mm mn mo mp mq mr ms mt mu mv mw mx my mz na nb nc fo bj"
                        data-selectable-paragraph=""
                    >
                        Newman provides different ways to run the postman
                        collection. Refer following for the same:<br />1) Users
                        can export the collection as JSON file and later Newman
                        can use that file as argument to run the collection<br />2)
                        Users can get the collection URL from postman and later
                        Newman can use that URL as argument to run the
                        collection
                    </p>
                    <p
                        id="5ac8"
                        class="pw-post-body-paragraph mf mg fv mh b mi mj mk ml mm mn mo mp mq mr ms mt mu mv mw mx my mz na nb nc fo bj"
                        data-selectable-paragraph=""
                    >
                        Refer below GIFs to export the collection and get the
                        collection URL:
                    </p>
                    <figure class="ob oc od oe of ly lq lr paragraph-image">
                        <div class="lq lr oq">
                            <picture
                                ><img
                                    alt=""
                                    class="bg ky lz c"
                                    width="640"
                                    height="400"
                                    loading="lazy"
                                    role="presentation"
                                    src="https://miro.medium.com/v2/resize:fit:640/1*aRqQYQH5mUc9VdaR2BLLkQ.gif"
                            /></picture>
                        </div>
                        <figcaption
                            class="ma mb mc lq lr md me be b bf z dw"
                            data-selectable-paragraph=""
                        >
                            Exporting Collection
                        </figcaption>
                    </figure>
                    <figure class="ob oc od oe of ly lq lr paragraph-image">
                        <div class="lq lr oq">
                            <picture
                                ><img
                                    alt=""
                                    class="bg ky lz c"
                                    width="640"
                                    height="400"
                                    loading="lazy"
                                    role="presentation"
                                    src="https://miro.medium.com/v2/resize:fit:640/1*l-I_UpBRTi-10DItq6wuIA.gif"
                            /></picture>
                        </div>
                        <figcaption
                            class="ma mb mc lq lr md me be b bf z dw"
                            data-selectable-paragraph=""
                        >
                            Getting Collection URL
                        </figcaption>
                    </figure>
                    <h1
                        id="71a6"
                        class="nd ne fv be nf ng nh ni nj nk nl nm nn no np nq nr ns nt nu nv nw nx ny nz oa bj"
                        data-selectable-paragraph=""
                    >
                        Newman Usage
                    </h1>
                    <p
                        id="38b9"
                        class="pw-post-body-paragraph mf mg fv mh b mi or mk ml mm os mo mp mq ot ms mt mu ou mw mx my ov na nb nc fo bj"
                        data-selectable-paragraph=""
                    >
                        Execute below command to use exported JSON to run the
                        collection:
                    </p>
                    <pre
                        class="ob oc od oe of og oh oi oj ax ok bj"
                    ><span id="88b5" class="ol ne fv oh b hp om on l oo op" data-selectable-paragraph="">newman run mycollection.json </span></pre>
                    <p
                        id="5893"
                        class="pw-post-body-paragraph mf mg fv mh b mi mj mk ml mm mn mo mp mq mr ms mt mu mv mw mx my mz na nb nc fo bj"
                        data-selectable-paragraph=""
                    >
                        Execute below command to use public URL to run the
                        collection:
                    </p>
                    <pre
                        class="ob oc od oe of og oh oi oj ax ok bj"
                    ><span id="cc8a" class="ol ne fv oh b hp om on l oo op" data-selectable-paragraph="">newman run <a class="af ow" href="https://www.postman.com/collections/cb208e7e64056f5294e5" rel="noopener ugc nofollow" target="_blank">https://www.postman.com/collections/cb208e7e64056f5294e5</a></span></pre>
                    <p
                        id="e46a"
                        class="pw-post-body-paragraph mf mg fv mh b mi mj mk ml mm mn mo mp mq mr ms mt mu mv mw mx my mz na nb nc fo bj"
                        data-selectable-paragraph=""
                    >
                        Output after the command execution will have PASS/FAIL
                        status for each API request. It will have the summary
                        table of the execution result. Refer below screenshot
                        for the output sample:
                    </p>
                </div>
            </div>
            <div class="ly">
                <div class="ab ca">
                    <div class="kt ox ku oy kv oz ce pa cf pb ch bg">
                        <div class="ob oc od oe of ab jl">
                            <figure
                                class="ki ly pc pd pe pf pg paragraph-image"
                            >
                                <div
                                    role="button"
                                    tabindex="0"
                                    class="ph pi ef pj bg pk"
                                >
                                    <picture
                                        ><img
                                            alt=""
                                            class="bg ky lz c"
                                            width="500"
                                            height="400"
                                            loading="eager"
                                            role="presentation"
                                            src="https://miro.medium.com/v2/resize:fit:2880/1*fcglMPLTkXQrndgTghRcSw.png"
                                    /></picture>
                                </div>
                            </figure>
                            <figure
                                class="ki ly pc pd pe pf pg paragraph-image"
                            >
                                <div
                                    role="button"
                                    tabindex="0"
                                    class="ph pi ef pj bg pk"
                                >
                                    <picture
                                        ><img
                                            alt=""
                                            class="bg ky lz c"
                                            width="500"
                                            height="400"
                                            loading="eager"
                                            role="presentation"
                                            src="https://miro.medium.com/v2/resize:fit:2880/1*X3JkCruS9DL9SPpJL5NPjw.png"
                                    /></picture>
                                </div>
                                <figcaption
                                    class="ma mb mc lq lr md me be b bf z dw pl ef pm pn"
                                    data-selectable-paragraph=""
                                >
                                    Sample Output
                                </figcaption>
                            </figure>
                        </div>
                    </div>
                </div>
            </div>
            <div class="ab ca">
                <div class="ch bg fa fb fc fd">
                    <p
                        id="58fa"
                        class="pw-post-body-paragraph mf mg fv mh b mi mj mk ml mm mn mo mp mq mr ms mt mu mv mw mx my mz na nb nc fo bj"
                        data-selectable-paragraph=""
                    >
                        Your collection might contain environment variables. To
                        run Newman with the environment, users can export the
                        environment from postman and later use that exported
                        environment file with -e flag.
                    </p>
                    <p
                        id="f946"
                        class="pw-post-body-paragraph mf mg fv mh b mi mj mk ml mm mn mo mp mq mr ms mt mu mv mw mx my mz na nb nc fo bj"
                        data-selectable-paragraph=""
                    >
                        Refer below command:
                    </p>
                    <pre
                        class="ob oc od oe of og oh oi oj ax ok bj"
                    ><span id="290e" class="ol ne fv oh b hp om on l oo op" data-selectable-paragraph="">newman run <a class="af ow" href="https://www.postman.com/collections/cb208e7e64056f5294e5" rel="noopener ugc nofollow" target="_blank">https://www.postman.com/collections/cb208e7e64056f5294e5</a> -e environment.json</span></pre>
                    <p
                        id="1f82"
                        class="pw-post-body-paragraph mf mg fv mh b mi mj mk ml mm mn mo mp mq mr ms mt mu mv mw mx my mz na nb nc fo bj"
                        data-selectable-paragraph=""
                    >
                        Refer below GIF to export the environment:
                    </p>
                    <figure class="ob oc od oe of ly lq lr paragraph-image">
                        <div class="lq lr oq">
                            <picture
                                ><img
                                    alt=""
                                    class="bg ky lz c"
                                    width="640"
                                    height="400"
                                    loading="lazy"
                                    role="presentation"
                                    src="https://miro.medium.com/v2/resize:fit:640/1*YehkX3pHxpACoYVYi7dWcw.gif"
                            /></picture>
                        </div>
                        <figcaption
                            class="ma mb mc lq lr md me be b bf z dw"
                            data-selectable-paragraph=""
                        >
                            Exporting Environment
                        </figcaption>
                    </figure>
                    <p
                        id="a9c4"
                        class="pw-post-body-paragraph mf mg fv mh b mi mj mk ml mm mn mo mp mq mr ms mt mu mv mw mx my mz na nb nc fo bj"
                        data-selectable-paragraph=""
                    >
                        Refer more options at
                        <a
                            class="af ow"
                            href="https://learning.postman.com/docs/running-collections/using-newman-cli/command-line-integration-with-newman/"
                            rel="noopener ugc nofollow"
                            target="_blank"
                            >https://learning.postman.com/docs/running-collections/using-newman-cli/command-line-integration-with-newman/</a
                        >
                    </p>
                    <p
                        id="6647"
                        class="pw-post-body-paragraph mf mg fv mh b mi mj mk ml mm mn mo mp mq mr ms mt mu mv mw mx my mz na nb nc fo bj"
                        data-selectable-paragraph=""
                    >
                        Till now we discussed on how can we run postman
                        collection using Newman. Now, we will discuss how can we
                        integrate the postman collection with Jenkins.
                        Traditionally we get the console output in table view.
                        Results in a good HTML report is always a better option
                        than console output. Found one node library which does
                        that pretty well. It is called newman-reporter-htmlextra
                        which is also built on Node.js. If node is already
                        installed on your machine, you can download the library
                        using below command:
                    </p>
                    <h1
                        id="f438"
                        class="nd ne fv be nf ng nh ni nj nk nl nm nn no np nq nr ns nt nu nv nw nx ny nz oa bj"
                        data-selectable-paragraph=""
                    >
                        HTMLextra Report Installation
                    </h1>
                    <pre
                        class="ob oc od oe of og oh oi oj ax ok bj"
                    ><span id="90f1" class="ol ne fv oh b hp om on l oo op" data-selectable-paragraph="">npm install -g newman-reporter-htmlextra</span></pre>
                    <p
                        id="6bb3"
                        class="pw-post-body-paragraph mf mg fv mh b mi mj mk ml mm mn mo mp mq mr ms mt mu mv mw mx my mz na nb nc fo bj"
                        data-selectable-paragraph=""
                    >
                        Once the library is installed, you can use that library
                        to generate reports. You can use -r flag with the
                        htmlextra as argument with newman command to generate
                        the report.
                    </p>
                    <h1
                        id="0322"
                        class="nd ne fv be nf ng nh ni nj nk nl nm nn no np nq nr ns nt nu nv nw nx ny nz oa bj"
                        data-selectable-paragraph=""
                    >
                        HTMLextra Report Usage
                    </h1>
                    <pre
                        class="ob oc od oe of og oh oi oj ax ok bj"
                    ><span id="6cd9" class="ol ne fv oh b hp om on l oo op" data-selectable-paragraph="">newman run collection.json -r htmlextra</span></pre>
                    <p
                        id="3a14"
                        class="pw-post-body-paragraph mf mg fv mh b mi mj mk ml mm mn mo mp mq mr ms mt mu mv mw mx my mz na nb nc fo bj"
                        data-selectable-paragraph=""
                    >
                        Note: Report will be generated in the directory from
                        where you have executed the command.
                    </p>
                    <p
                        id="1e54"
                        class="pw-post-body-paragraph mf mg fv mh b mi mj mk ml mm mn mo mp mq mr ms mt mu mv mw mx my mz na nb nc fo bj"
                        data-selectable-paragraph=""
                    >
                        Sample report will look like below screenshot.
                    </p>
                    <figure class="ob oc od oe of ly lq lr paragraph-image">
                        <div
                            role="button"
                            tabindex="0"
                            class="ph pi ef pj bg pk"
                        >
                            <div class="lq lr po">
                                <picture
                                    ><img
                                        alt=""
                                        class="bg ky lz c"
                                        width="700"
                                        height="530"
                                        loading="lazy"
                                        role="presentation"
                                        src="https://miro.medium.com/v2/resize:fit:700/1*rHYEQjnY_v_DHDKzuJ_q2Q.png"
                                /></picture>
                            </div>
                        </div>
                        <figcaption
                            class="ma mb mc lq lr md me be b bf z dw"
                            data-selectable-paragraph=""
                        >
                            Sample Report
                        </figcaption>
                    </figure>
                    <p
                        id="6f30"
                        class="pw-post-body-paragraph mf mg fv mh b mi mj mk ml mm mn mo mp mq mr ms mt mu mv mw mx my mz na nb nc fo bj"
                        data-selectable-paragraph=""
                    >
                        Refer
                        <a
                            class="af ow"
                            href="https://www.npmjs.com/package/newman-reporter-htmlextra"
                            rel="noopener ugc nofollow"
                            target="_blank"
                            >https://www.npmjs.com/package/newman-reporter-htmlextra</a
                        >
                        to know more options and other details of the library.
                    </p>
                    <h1
                        id="f9ed"
                        class="nd ne fv be nf ng nh ni nj nk nl nm nn no np nq nr ns nt nu nv nw nx ny nz oa bj"
                        data-selectable-paragraph=""
                    >
                        Jenkins Job Setup
                    </h1>
                    <p
                        id="71e5"
                        class="pw-post-body-paragraph mf mg fv mh b mi or mk ml mm os mo mp mq ot ms mt mu ou mw mx my ov na nb nc fo bj"
                        data-selectable-paragraph=""
                    >
                        We will configure Jenkins job with 2 simple steps. Refer
                        below steps for the same:
                    </p>
                    <p
                        id="db88"
                        class="pw-post-body-paragraph mf mg fv mh b mi mj mk ml mm mn mo mp mq mr ms mt mu mv mw mx my mz na nb nc fo bj"
                        data-selectable-paragraph=""
                    >
                        1) Add the build step with execute shell option. Enter
                        newman command that we want to be executed to run
                        postman collection.
                    </p>
                    <pre
                        class="ob oc od oe of og oh oi oj ax ok bj"
                    ><span id="b446" class="ol ne fv oh b hp om on l oo op" data-selectable-paragraph="">newman run collection.json -r htmlextra — reporter-htmlextra-export “newman/report.html”</span></pre>
                    <p
                        id="9ed6"
                        class="pw-post-body-paragraph mf mg fv mh b mi mj mk ml mm mn mo mp mq mr ms mt mu mv mw mx my mz na nb nc fo bj"
                        data-selectable-paragraph=""
                    >
                        Note: Report will generate under newman/report.html.
                    </p>
                    <p
                        id="d09f"
                        class="pw-post-body-paragraph mf mg fv mh b mi mj mk ml mm mn mo mp mq mr ms mt mu mv mw mx my mz na nb nc fo bj"
                        data-selectable-paragraph=""
                    >
                        2) Next step is post-build actions. We will add Publish
                        HTML reports post-build actions to publish HTML reports
                        that your build generates to the job and build pages.
                    </p>
                    <p
                        id="8231"
                        class="pw-post-body-paragraph mf mg fv mh b mi mj mk ml mm mn mo mp mq mr ms mt mu mv mw mx my mz na nb nc fo bj"
                        data-selectable-paragraph=""
                    >
                        Refer below GIF to configure the whole Jenkins job.
                    </p>
                    <figure class="ob oc od oe of ly lq lr paragraph-image">
                        <div class="lq lr oq">
                            <picture
                                ><img
                                    alt=""
                                    class="bg ky lz c"
                                    width="640"
                                    height="400"
                                    loading="lazy"
                                    role="presentation"
                                    src="https://miro.medium.com/v2/resize:fit:640/1*3IqwXpWBrcDn8r3ftSZf3g.gif"
                            /></picture>
                        </div>
                        <figcaption
                            class="ma mb mc lq lr md me be b bf z dw"
                            data-selectable-paragraph=""
                        >
                            Jenkins Job Setup
                        </figcaption>
                    </figure>
                </div>
            </div>
        </div>
    </div>
</section>
