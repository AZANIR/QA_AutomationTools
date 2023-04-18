<section><div><div class="es gk gl gm gn go"></div><div class="gp gq gr gs gt"><div class=""><h1 id="94d1" class="pw-post-title gu gv gw bd gx gy gz ha hb hc hd he hf hg hh hi hj hk hl hm hn ho hp hq hr hs bi" data-selectable-paragraph="">How to set GitBash as the default NPM script runner on Windows</h1></div><figure class="ec ee hu hv hw hx dy dz paragraph-image"><div role="button" tabindex="0" class="hy hz di ia bf ib"><div class="dy dz ht"><picture><source srcset="https://miro.medium.com/max/640/1*3kk2hmD9uFB2eH3RiAOA0g.webp 640w, https://miro.medium.com/max/720/1*3kk2hmD9uFB2eH3RiAOA0g.webp 720w, https://miro.medium.com/max/750/1*3kk2hmD9uFB2eH3RiAOA0g.webp 750w, https://miro.medium.com/max/786/1*3kk2hmD9uFB2eH3RiAOA0g.webp 786w, https://miro.medium.com/max/828/1*3kk2hmD9uFB2eH3RiAOA0g.webp 828w, https://miro.medium.com/max/1100/1*3kk2hmD9uFB2eH3RiAOA0g.webp 1100w, https://miro.medium.com/max/1400/1*3kk2hmD9uFB2eH3RiAOA0g.webp 1400w" sizes="(min-resolution: 4dppx) and (max-width: 700px) 50vw, (-webkit-min-device-pixel-ratio: 4) and (max-width: 700px) 50vw, (min-resolution: 3dppx) and (max-width: 700px) 67vw, (-webkit-min-device-pixel-ratio: 3) and (max-width: 700px) 65vw, (min-resolution: 2.5dppx) and (max-width: 700px) 80vw, (-webkit-min-device-pixel-ratio: 2.5) and (max-width: 700px) 80vw, (min-resolution: 2dppx) and (max-width: 700px) 100vw, (-webkit-min-device-pixel-ratio: 2) and (max-width: 700px) 100vw, 700px" type="image/webp"><source data-testid="og" srcset="https://miro.medium.com/max/640/1*3kk2hmD9uFB2eH3RiAOA0g.png 640w, https://miro.medium.com/max/720/1*3kk2hmD9uFB2eH3RiAOA0g.png 720w, https://miro.medium.com/max/750/1*3kk2hmD9uFB2eH3RiAOA0g.png 750w, https://miro.medium.com/max/786/1*3kk2hmD9uFB2eH3RiAOA0g.png 786w, https://miro.medium.com/max/828/1*3kk2hmD9uFB2eH3RiAOA0g.png 828w, https://miro.medium.com/max/1100/1*3kk2hmD9uFB2eH3RiAOA0g.png 1100w, https://miro.medium.com/max/1400/1*3kk2hmD9uFB2eH3RiAOA0g.png 1400w" sizes="(min-resolution: 4dppx) and (max-width: 700px) 50vw, (-webkit-min-device-pixel-ratio: 4) and (max-width: 700px) 50vw, (min-resolution: 3dppx) and (max-width: 700px) 67vw, (-webkit-min-device-pixel-ratio: 3) and (max-width: 700px) 65vw, (min-resolution: 2.5dppx) and (max-width: 700px) 80vw, (-webkit-min-device-pixel-ratio: 2.5) and (max-width: 700px) 80vw, (min-resolution: 2dppx) and (max-width: 700px) 100vw, (-webkit-min-device-pixel-ratio: 2) and (max-width: 700px) 100vw, 700px"><img alt="" class="bf ic id c" width="700" height="338" loading="eager" role="presentation" src="https://miro.medium.com/max/700/1*3kk2hmD9uFB2eH3RiAOA0g.png"></picture></div></div></figure><h1 id="e3cb" class="ie if gw bd ig ih ii ij ik il im in io ip iq ir is it iu iv iw ix iy iz ja jb bi" data-selectable-paragraph="">The issue</h1><p id="bd4c" class="pw-post-body-paragraph jc jd gw je b jf jg jh ji jj jk jl jm jn jo jp jq jr js jt ju jv jw jx jy jz gp bi" data-selectable-paragraph="">As a Windows user, you may face some issues trying to run NPM scripts that contain shell syntax.</p><figure class="kb kc kd ke ek hx dy dz paragraph-image"><div class="dy dz ka"><picture><source srcset="https://miro.medium.com/max/640/1*UgwHSZsqjfUwUDv-EAb03w.webp 640w, https://miro.medium.com/max/720/1*UgwHSZsqjfUwUDv-EAb03w.webp 720w, https://miro.medium.com/max/750/1*UgwHSZsqjfUwUDv-EAb03w.webp 750w, https://miro.medium.com/max/786/1*UgwHSZsqjfUwUDv-EAb03w.webp 786w, https://miro.medium.com/max/828/1*UgwHSZsqjfUwUDv-EAb03w.webp 828w, https://miro.medium.com/max/1100/1*UgwHSZsqjfUwUDv-EAb03w.webp 1100w, https://miro.medium.com/max/634/1*UgwHSZsqjfUwUDv-EAb03w.webp 634w" sizes="(min-resolution: 4dppx) and (max-width: 700px) 50vw, (-webkit-min-device-pixel-ratio: 4) and (max-width: 700px) 50vw, (min-resolution: 3dppx) and (max-width: 700px) 67vw, (-webkit-min-device-pixel-ratio: 3) and (max-width: 700px) 65vw, (min-resolution: 2.5dppx) and (max-width: 700px) 80vw, (-webkit-min-device-pixel-ratio: 2.5) and (max-width: 700px) 80vw, (min-resolution: 2dppx) and (max-width: 700px) 100vw, (-webkit-min-device-pixel-ratio: 2) and (max-width: 700px) 100vw, 317px" type="image/webp"><source data-testid="og" srcset="https://miro.medium.com/max/640/1*UgwHSZsqjfUwUDv-EAb03w.png 640w, https://miro.medium.com/max/720/1*UgwHSZsqjfUwUDv-EAb03w.png 720w, https://miro.medium.com/max/750/1*UgwHSZsqjfUwUDv-EAb03w.png 750w, https://miro.medium.com/max/786/1*UgwHSZsqjfUwUDv-EAb03w.png 786w, https://miro.medium.com/max/828/1*UgwHSZsqjfUwUDv-EAb03w.png 828w, https://miro.medium.com/max/1100/1*UgwHSZsqjfUwUDv-EAb03w.png 1100w, https://miro.medium.com/max/634/1*UgwHSZsqjfUwUDv-EAb03w.png 634w" sizes="(min-resolution: 4dppx) and (max-width: 700px) 50vw, (-webkit-min-device-pixel-ratio: 4) and (max-width: 700px) 50vw, (min-resolution: 3dppx) and (max-width: 700px) 67vw, (-webkit-min-device-pixel-ratio: 3) and (max-width: 700px) 65vw, (min-resolution: 2.5dppx) and (max-width: 700px) 80vw, (-webkit-min-device-pixel-ratio: 2.5) and (max-width: 700px) 80vw, (min-resolution: 2dppx) and (max-width: 700px) 100vw, (-webkit-min-device-pixel-ratio: 2) and (max-width: 700px) 100vw, 317px"><img alt="" class="bf ic id c" width="317" height="17" loading="lazy" role="presentation" src="https://miro.medium.com/max/317/1*UgwHSZsqjfUwUDv-EAb03w.png"></picture></div></figure><p id="f822" class="pw-post-body-paragraph jc jd gw je b jf kf jh ji jj kg jl jm jn kh jp jq jr ki jt ju jv kj jx jy jz gp bi" data-selectable-paragraph="">Even if you try to use PowerShell, you may face syntax errors.</p><figure class="kb kc kd ke ek hx dy dz paragraph-image"><div class="dy dz kk"><picture><source srcset="https://miro.medium.com/max/640/1*6zp48S5rcNEjn79fTRwo7A.webp 640w, https://miro.medium.com/max/720/1*6zp48S5rcNEjn79fTRwo7A.webp 720w, https://miro.medium.com/max/750/1*6zp48S5rcNEjn79fTRwo7A.webp 750w, https://miro.medium.com/max/786/1*6zp48S5rcNEjn79fTRwo7A.webp 786w, https://miro.medium.com/max/828/1*6zp48S5rcNEjn79fTRwo7A.webp 828w, https://miro.medium.com/max/1100/1*6zp48S5rcNEjn79fTRwo7A.webp 1100w, https://miro.medium.com/max/358/1*6zp48S5rcNEjn79fTRwo7A.webp 358w" sizes="(min-resolution: 4dppx) and (max-width: 700px) 50vw, (-webkit-min-device-pixel-ratio: 4) and (max-width: 700px) 50vw, (min-resolution: 3dppx) and (max-width: 700px) 67vw, (-webkit-min-device-pixel-ratio: 3) and (max-width: 700px) 65vw, (min-resolution: 2.5dppx) and (max-width: 700px) 80vw, (-webkit-min-device-pixel-ratio: 2.5) and (max-width: 700px) 80vw, (min-resolution: 2dppx) and (max-width: 700px) 100vw, (-webkit-min-device-pixel-ratio: 2) and (max-width: 700px) 100vw, 179px" type="image/webp"><source data-testid="og" srcset="https://miro.medium.com/max/640/1*6zp48S5rcNEjn79fTRwo7A.png 640w, https://miro.medium.com/max/720/1*6zp48S5rcNEjn79fTRwo7A.png 720w, https://miro.medium.com/max/750/1*6zp48S5rcNEjn79fTRwo7A.png 750w, https://miro.medium.com/max/786/1*6zp48S5rcNEjn79fTRwo7A.png 786w, https://miro.medium.com/max/828/1*6zp48S5rcNEjn79fTRwo7A.png 828w, https://miro.medium.com/max/1100/1*6zp48S5rcNEjn79fTRwo7A.png 1100w, https://miro.medium.com/max/358/1*6zp48S5rcNEjn79fTRwo7A.png 358w" sizes="(min-resolution: 4dppx) and (max-width: 700px) 50vw, (-webkit-min-device-pixel-ratio: 4) and (max-width: 700px) 50vw, (min-resolution: 3dppx) and (max-width: 700px) 67vw, (-webkit-min-device-pixel-ratio: 3) and (max-width: 700px) 65vw, (min-resolution: 2.5dppx) and (max-width: 700px) 80vw, (-webkit-min-device-pixel-ratio: 2.5) and (max-width: 700px) 80vw, (min-resolution: 2dppx) and (max-width: 700px) 100vw, (-webkit-min-device-pixel-ratio: 2) and (max-width: 700px) 100vw, 179px"><img alt="" class="bf ic id c" width="179" height="17" loading="lazy" role="presentation" src="https://miro.medium.com/max/179/1*6zp48S5rcNEjn79fTRwo7A.png"></picture></div></figure><p id="5022" class="pw-post-body-paragraph jc jd gw je b jf kf jh ji jj kg jl jm jn kh jp jq jr ki jt ju jv kj jx jy jz gp bi" data-selectable-paragraph="">Ok, we know the CMD is legacy and it’s not able to run any code written in shell-script, <strong class="je gx">but</strong> how about Powershell?</p><h1 id="1c2f" class="ie if gw bd ig ih ii ij ik il im in io ip iq ir is it iu iv iw ix iy iz ja jb bi" data-selectable-paragraph="">The “but”</h1><p id="27de" class="pw-post-body-paragraph jc jd gw je b jf jg jh ji jj jk jl jm jn jo jp jq jr js jt ju jv jw jx jy jz gp bi" data-selectable-paragraph="">Isn’t Powershell able to run shell-script properly? The answer is YES. But, there are some tricky details about how NPM runs its scripts.</p><p id="856f" class="pw-post-body-paragraph jc jd gw je b jf kf jh ji jj kg jl jm jn kh jp jq jr ki jt ju jv kj jx jy jz gp bi" data-selectable-paragraph="">Internally NPM runs your scripts on the default command terminal, independently from where you are triggering the scripts.</p></div><div class="ab cl kl km gd kn" role="separator"><span class="ko bw bk kp kq kr"></span><span class="ko bw bk kp kq kr"></span><span class="ko bw bk kp kq"></span></div><div class="gp gq gr gs gt"><blockquote class="ks kt ku"><p id="7403" class="jc jd kv je b jf kf jh ji jj kg jl jm kw kh jp jq kx ki jt ju ky kj jx jy jz gp bi" data-selectable-paragraph="">This fact could confuse you a lot. You may think once you are running the script from PowerShell you will be able to run shell-script syntax. 💥</p></blockquote></div><div class="ab cl kl km gd kn" role="separator"><span class="ko bw bk kp kq kr"></span><span class="ko bw bk kp kq kr"></span><span class="ko bw bk kp kq"></span></div><div class="gp gq gr gs gt"><p id="7192" class="pw-post-body-paragraph jc jd gw je b jf kf jh ji jj kg jl jm jn kh jp jq jr ki jt ju jv kj jx jy jz gp bi" data-selectable-paragraph="">On Windows, it means it runs every script on CMD, and as I said before it’s not compatible with shell-script syntax.</p><h1 id="ab17" class="ie if gw bd ig ih ii ij ik il im in io ip iq ir is it iu iv iw ix iy iz ja jb bi" data-selectable-paragraph="">The solution</h1><p id="0ffb" class="pw-post-body-paragraph jc jd gw je b jf jg jh ji jj jk jl jm jn jo jp jq jr js jt ju jv jw jx jy jz gp bi" data-selectable-paragraph="">The solution for it is pretty simple, you just need to set a shell-script syntax compatible terminal as the default NPM script runner.</p><p id="8690" class="pw-post-body-paragraph jc jd gw je b jf kf jh ji jj kg jl jm jn kh jp jq jr ki jt ju jv kj jx jy jz gp bi" data-selectable-paragraph="">I know I am talking about Powershell since the beginning, but I will personally recommend you to use GitBash, so check below how to set it as your default NPM script runner.</p></div><div class="ab cl kl km gd kn" role="separator"><span class="ko bw bk kp kq kr"></span><span class="ko bw bk kp kq kr"></span><span class="ko bw bk kp kq"></span></div><div class="gp gq gr gs gt"><p id="0802" class="pw-post-body-paragraph jc jd gw je b jf kf jh ji jj kg jl jm jn kh jp jq jr ki jt ju jv kj jx jy jz gp bi" data-selectable-paragraph="">Open your cmd and run:</p><pre class="kb kc kd ke ek kz la lb lc aw ld bi"><span id="e544" class="le if gw la b eu lf lg l lh li" data-selectable-paragraph="">npm config set script-shell "C:\\Program Files (x86)\\git\\bin\\bash.exe"</span></pre><p id="3a57" class="pw-post-body-paragraph jc jd gw je b jf kf jh ji jj kg jl jm jn kh jp jq jr ki jt ju jv kj jx jy jz gp bi" data-selectable-paragraph="">For x64 installations</p><pre class="kb kc kd ke ek kz la lb lc aw ld bi"><span id="6b54" class="le if gw la b eu lf lg l lh li" data-selectable-paragraph="">npm config set script-shell "C:\\Program Files\\git\\bin\\bash.exe"</span></pre></div><div class="ab cl kl km gd kn" role="separator"><span class="ko bw bk kp kq kr"></span><span class="ko bw bk kp kq kr"></span><span class="ko bw bk kp kq"></span></div><div class="gp gq gr gs gt"><blockquote class="ks kt ku"><p id="f5fa" class="jc jd kv je b jf kf jh ji jj kg jl jm kw kh jp jq kx ki jt ju ky kj jx jy jz gp bi" data-selectable-paragraph="">With this solution, I am considering you have GitBash installed at these locations. Always check before if it’s the location your GitBash is installed. Otherwise, you must change the path used on these examples by your current GitBash directory path.</p></blockquote><h1 id="c3f1" class="ie if gw bd ig ih ii ij ik il im in io ip iq ir is it iu iv iw ix iy iz ja jb bi" data-selectable-paragraph="">Need to revert?</h1><p id="31aa" class="pw-post-body-paragraph jc jd gw je b jf jg jh ji jj jk jl jm jn jo jp jq jr js jt ju jv jw jx jy jz gp bi" data-selectable-paragraph="">If you need to revert the configuration presented before, don’t worry. Run the following command to accomplish it.</p><pre class="kb kc kd ke ek kz la lb lc aw ld bi"><span id="ca99" class="le if gw la b eu lf lg l lh li" data-selectable-paragraph="">npm config delete script-shell</span></pre><h2 id="7a8b" class="le if gw bd ig lj lk ll ik lm ln lo io jn lp lq is jr lr ls iw jv lt lu ja lv bi" data-selectable-paragraph="">That’s all folks.</h2></div></div></section>