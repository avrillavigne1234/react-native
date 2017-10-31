---
id: version-0.44-refreshcontrol
title: refreshcontrol
original_id: refreshcontrol
---
<a id="content"></a><h1><a class="anchor" name="refreshcontrol"></a>RefreshControl <a class="hash-link" href="docs/refreshcontrol.html#refreshcontrol">#</a></h1><div><div><p>This component is used inside a ScrollView or ListView to add pull to refresh
functionality. When the ScrollView is at <code>scrollY: 0</code>, swiping down
triggers an <code>onRefresh</code> event.</p><h3><a class="anchor" name="usage-example"></a>Usage example <a class="hash-link" href="docs/refreshcontrol.html#usage-example">#</a></h3><div class="prism language-javascript">class <span class="token class-name">RefreshableList</span> extends <span class="token class-name">Component</span> <span class="token punctuation">{</span>
  <span class="token function">constructor<span class="token punctuation">(</span></span>props<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token function">super<span class="token punctuation">(</span></span>props<span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token keyword">this</span><span class="token punctuation">.</span>state <span class="token operator">=</span> <span class="token punctuation">{</span>
      refreshing<span class="token punctuation">:</span> <span class="token boolean">false</span><span class="token punctuation">,</span>
    <span class="token punctuation">}</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span>

  <span class="token function">_onRefresh<span class="token punctuation">(</span></span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">this</span><span class="token punctuation">.</span><span class="token function">setState<span class="token punctuation">(</span></span><span class="token punctuation">{</span>refreshing<span class="token punctuation">:</span> <span class="token boolean">true</span><span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token function">fetchData<span class="token punctuation">(</span></span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token function">then<span class="token punctuation">(</span></span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">=</span><span class="token operator">&gt;</span> <span class="token punctuation">{</span>
      <span class="token keyword">this</span><span class="token punctuation">.</span><span class="token function">setState<span class="token punctuation">(</span></span><span class="token punctuation">{</span>refreshing<span class="token punctuation">:</span> <span class="token boolean">false</span><span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span>

  <span class="token function">render<span class="token punctuation">(</span></span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">return</span> <span class="token punctuation">(</span>
      &lt;ListView
        refreshControl<span class="token operator">=</span><span class="token punctuation">{</span>
          &lt;RefreshControl
            refreshing<span class="token operator">=</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>refreshing<span class="token punctuation">}</span>
            onRefresh<span class="token operator">=</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>_onRefresh<span class="token punctuation">.</span><span class="token function">bind<span class="token punctuation">(</span></span><span class="token keyword">this</span><span class="token punctuation">)</span><span class="token punctuation">}</span>
          <span class="token operator">/</span><span class="token operator">&gt;</span>
        <span class="token punctuation">}</span>
        <span class="token punctuation">.</span><span class="token punctuation">.</span><span class="token punctuation">.</span>
      <span class="token operator">&gt;</span>
      <span class="token punctuation">.</span><span class="token punctuation">.</span><span class="token punctuation">.</span>
      &lt;<span class="token operator">/</span>ListView<span class="token operator">&gt;</span>
    <span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span>
  <span class="token punctuation">.</span><span class="token punctuation">.</span><span class="token punctuation">.</span>
<span class="token punctuation">}</span></div><p><strong>Note:</strong> <code>refreshing</code> is a controlled prop, this is why it needs to be set to true
in the <code>onRefresh</code> function otherwise the refresh indicator will stop immediately.</p></div><h3><a class="anchor" name="props"></a>Props <a class="hash-link" href="docs/refreshcontrol.html#props">#</a></h3><div class="props"><div class="prop"><h4 class="propTitle"><a class="anchor" name="viewproptypes"></a><a href="docs/viewproptypes.html#props">ViewPropTypes props...</a> <a class="hash-link" href="docs/refreshcontrol.html#viewproptypes">#</a></h4></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="onrefresh"></a>onRefresh?: <span class="propType">function</span> <a class="hash-link" href="docs/refreshcontrol.html#onrefresh">#</a></h4><div><p>Called when the view starts refreshing.</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="refreshing"></a>refreshing: <span class="propType">bool</span> <a class="hash-link" href="docs/refreshcontrol.html#refreshing">#</a></h4><div><p>Whether the view should be indicating an active refresh.</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="colors"></a><span class="platform">android</span>colors?: <span class="propType"><span>[<a href="docs/colors.html">color</a>]</span></span> <a class="hash-link" href="docs/refreshcontrol.html#colors">#</a></h4><div><p>The colors (at least one) that will be used to draw the refresh indicator.</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="enabled"></a><span class="platform">android</span>enabled?: <span class="propType">bool</span> <a class="hash-link" href="docs/refreshcontrol.html#enabled">#</a></h4><div><p>Whether the pull to refresh functionality is enabled.</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="progressbackgroundcolor"></a><span class="platform">android</span>progressBackgroundColor?: <span class="propType"><a href="docs/colors.html">color</a></span> <a class="hash-link" href="docs/refreshcontrol.html#progressbackgroundcolor">#</a></h4><div><p>The background color of the refresh indicator.</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="progressviewoffset"></a><span class="platform">android</span>progressViewOffset?: <span class="propType">number</span> <a class="hash-link" href="docs/refreshcontrol.html#progressviewoffset">#</a></h4><div><p>Progress view top offset</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="size"></a><span class="platform">android</span>size?: <span class="propType">enum(RefreshLayoutConsts.SIZE.DEFAULT, RefreshLayoutConsts.SIZE.LARGE)</span> <a class="hash-link" href="docs/refreshcontrol.html#size">#</a></h4><div><p>Size of the refresh indicator, see RefreshControl.SIZE.</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="tintcolor"></a><span class="platform">ios</span>tintColor?: <span class="propType"><a href="docs/colors.html">color</a></span> <a class="hash-link" href="docs/refreshcontrol.html#tintcolor">#</a></h4><div><p>The color of the refresh indicator.</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="title"></a><span class="platform">ios</span>title?: <span class="propType">string</span> <a class="hash-link" href="docs/refreshcontrol.html#title">#</a></h4><div><p>The title displayed under the refresh indicator.</p></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="titlecolor"></a><span class="platform">ios</span>titleColor?: <span class="propType"><a href="docs/colors.html">color</a></span> <a class="hash-link" href="docs/refreshcontrol.html#titlecolor">#</a></h4><div><p>Title color.</p></div></div></div></div><p class="edit-page-block">You can <a target="_blank" href="https://github.com/facebook/react-native/blob/master/Libraries/Components/RefreshControl/RefreshControl.js">edit the content above on GitHub</a> and send us a pull request!</p><div><div><table width="100%"><tbody><tr><td><h3><a class="anchor" name="examples"></a>Examples <a class="hash-link" href="docs/refreshcontrol.html#examples">#</a></h3></td><td style="text-align:right;"><a target="_blank" href="https://github.com/facebook/react-native/blob/master/Examples/UIExplorer/js/RefreshControlExample.js">Edit on GitHub</a></td></tr></tbody></table><div class="example-container"><div class="prism language-javascript"><span class="token string">'use strict'</span><span class="token punctuation">;</span>

const React <span class="token operator">=</span> <span class="token function">require<span class="token punctuation">(</span></span><span class="token string">'react'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
const ReactNative <span class="token operator">=</span> <span class="token function">require<span class="token punctuation">(</span></span><span class="token string">'react-native'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
const <span class="token punctuation">{</span>
  ScrollView<span class="token punctuation">,</span>
  StyleSheet<span class="token punctuation">,</span>
  RefreshControl<span class="token punctuation">,</span>
  Text<span class="token punctuation">,</span>
  TouchableWithoutFeedback<span class="token punctuation">,</span>
  View<span class="token punctuation">,</span>
<span class="token punctuation">}</span> <span class="token operator">=</span> ReactNative<span class="token punctuation">;</span>

const styles <span class="token operator">=</span> StyleSheet<span class="token punctuation">.</span><span class="token function">create<span class="token punctuation">(</span></span><span class="token punctuation">{</span>
  row<span class="token punctuation">:</span> <span class="token punctuation">{</span>
    borderColor<span class="token punctuation">:</span> <span class="token string">'grey'</span><span class="token punctuation">,</span>
    borderWidth<span class="token punctuation">:</span> <span class="token number">1</span><span class="token punctuation">,</span>
    padding<span class="token punctuation">:</span> <span class="token number">20</span><span class="token punctuation">,</span>
    backgroundColor<span class="token punctuation">:</span> <span class="token string">'#3a5795'</span><span class="token punctuation">,</span>
    margin<span class="token punctuation">:</span> <span class="token number">5</span><span class="token punctuation">,</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>
  text<span class="token punctuation">:</span> <span class="token punctuation">{</span>
    alignSelf<span class="token punctuation">:</span> <span class="token string">'center'</span><span class="token punctuation">,</span>
    color<span class="token punctuation">:</span> <span class="token string">'#fff'</span><span class="token punctuation">,</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>
  scrollview<span class="token punctuation">:</span> <span class="token punctuation">{</span>
    flex<span class="token punctuation">:</span> <span class="token number">1</span><span class="token punctuation">,</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

class <span class="token class-name">Row</span> extends <span class="token class-name">React<span class="token punctuation">.</span>Component</span> <span class="token punctuation">{</span>
  _onClick <span class="token operator">=</span> <span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">=</span><span class="token operator">&gt;</span> <span class="token punctuation">{</span>
    <span class="token keyword">this</span><span class="token punctuation">.</span>props<span class="token punctuation">.</span><span class="token function">onClick<span class="token punctuation">(</span></span><span class="token keyword">this</span><span class="token punctuation">.</span>props<span class="token punctuation">.</span>data<span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">;</span>

  <span class="token function">render<span class="token punctuation">(</span></span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">return</span> <span class="token punctuation">(</span>
     &lt;TouchableWithoutFeedback onPress<span class="token operator">=</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>_onClick<span class="token punctuation">}</span> <span class="token operator">&gt;</span>
        &lt;View style<span class="token operator">=</span><span class="token punctuation">{</span>styles<span class="token punctuation">.</span>row<span class="token punctuation">}</span><span class="token operator">&gt;</span>
          &lt;Text style<span class="token operator">=</span><span class="token punctuation">{</span>styles<span class="token punctuation">.</span>text<span class="token punctuation">}</span><span class="token operator">&gt;</span>
            <span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>props<span class="token punctuation">.</span>data<span class="token punctuation">.</span>text <span class="token operator">+</span> <span class="token string">' ('</span> <span class="token operator">+</span> <span class="token keyword">this</span><span class="token punctuation">.</span>props<span class="token punctuation">.</span>data<span class="token punctuation">.</span>clicks <span class="token operator">+</span> <span class="token string">' clicks)'</span><span class="token punctuation">}</span>
          &lt;<span class="token operator">/</span>Text<span class="token operator">&gt;</span>
        &lt;<span class="token operator">/</span>View<span class="token operator">&gt;</span>
      &lt;<span class="token operator">/</span>TouchableWithoutFeedback<span class="token operator">&gt;</span>
    <span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span>
<span class="token punctuation">}</span>

class <span class="token class-name">RefreshControlExample</span> extends <span class="token class-name">React<span class="token punctuation">.</span>Component</span> <span class="token punctuation">{</span>
  static title <span class="token operator">=</span> <span class="token string">'&lt;RefreshControl&gt;'</span><span class="token punctuation">;</span>
  static description <span class="token operator">=</span> <span class="token string">'Adds pull-to-refresh support to a scrollview.'</span><span class="token punctuation">;</span>

  state <span class="token operator">=</span> <span class="token punctuation">{</span>
    isRefreshing<span class="token punctuation">:</span> <span class="token boolean">false</span><span class="token punctuation">,</span>
    loaded<span class="token punctuation">:</span> <span class="token number">0</span><span class="token punctuation">,</span>
    rowData<span class="token punctuation">:</span> Array<span class="token punctuation">.</span><span class="token function">from<span class="token punctuation">(</span></span><span class="token keyword">new</span> <span class="token class-name">Array</span><span class="token punctuation">(</span><span class="token number">20</span><span class="token punctuation">)</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token function">map<span class="token punctuation">(</span></span>
      <span class="token punctuation">(</span>val<span class="token punctuation">,</span> i<span class="token punctuation">)</span> <span class="token operator">=</span><span class="token operator">&gt;</span> <span class="token punctuation">(</span><span class="token punctuation">{</span>text<span class="token punctuation">:</span> <span class="token string">'Initial row '</span> <span class="token operator">+</span> i<span class="token punctuation">,</span> clicks<span class="token punctuation">:</span> <span class="token number">0</span><span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">)</span><span class="token punctuation">,</span>
  <span class="token punctuation">}</span><span class="token punctuation">;</span>

  _onClick <span class="token operator">=</span> <span class="token punctuation">(</span>row<span class="token punctuation">)</span> <span class="token operator">=</span><span class="token operator">&gt;</span> <span class="token punctuation">{</span>
    row<span class="token punctuation">.</span>clicks<span class="token operator">++</span><span class="token punctuation">;</span>
    <span class="token keyword">this</span><span class="token punctuation">.</span><span class="token function">setState<span class="token punctuation">(</span></span><span class="token punctuation">{</span>
      rowData<span class="token punctuation">:</span> <span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>rowData<span class="token punctuation">,</span>
    <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">;</span>

  <span class="token function">render<span class="token punctuation">(</span></span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    const rows <span class="token operator">=</span> <span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>rowData<span class="token punctuation">.</span><span class="token function">map<span class="token punctuation">(</span></span><span class="token punctuation">(</span>row<span class="token punctuation">,</span> ii<span class="token punctuation">)</span> <span class="token operator">=</span><span class="token operator">&gt;</span> <span class="token punctuation">{</span>
      <span class="token keyword">return</span> &lt;Row key<span class="token operator">=</span><span class="token punctuation">{</span>ii<span class="token punctuation">}</span> data<span class="token operator">=</span><span class="token punctuation">{</span>row<span class="token punctuation">}</span> onClick<span class="token operator">=</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>_onClick<span class="token punctuation">}</span><span class="token operator">/</span><span class="token operator">&gt;</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token keyword">return</span> <span class="token punctuation">(</span>
      &lt;ScrollView
        style<span class="token operator">=</span><span class="token punctuation">{</span>styles<span class="token punctuation">.</span>scrollview<span class="token punctuation">}</span>
        refreshControl<span class="token operator">=</span><span class="token punctuation">{</span>
          &lt;RefreshControl
            refreshing<span class="token operator">=</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>isRefreshing<span class="token punctuation">}</span>
            onRefresh<span class="token operator">=</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>_onRefresh<span class="token punctuation">}</span>
            tintColor<span class="token operator">=</span><span class="token string">"#ff0000"</span>
            title<span class="token operator">=</span><span class="token string">"Loading..."</span>
            titleColor<span class="token operator">=</span><span class="token string">"#00ff00"</span>
            colors<span class="token operator">=</span><span class="token punctuation">{</span><span class="token punctuation">[</span><span class="token string">'#ff0000'</span><span class="token punctuation">,</span> <span class="token string">'#00ff00'</span><span class="token punctuation">,</span> <span class="token string">'#0000ff'</span><span class="token punctuation">]</span><span class="token punctuation">}</span>
            progressBackgroundColor<span class="token operator">=</span><span class="token string">"#ffff00"</span>
          <span class="token operator">/</span><span class="token operator">&gt;</span>
        <span class="token punctuation">}</span><span class="token operator">&gt;</span>
        <span class="token punctuation">{</span>rows<span class="token punctuation">}</span>
      &lt;<span class="token operator">/</span>ScrollView<span class="token operator">&gt;</span>
    <span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span>

  _onRefresh <span class="token operator">=</span> <span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">=</span><span class="token operator">&gt;</span> <span class="token punctuation">{</span>
    <span class="token keyword">this</span><span class="token punctuation">.</span><span class="token function">setState<span class="token punctuation">(</span></span><span class="token punctuation">{</span>isRefreshing<span class="token punctuation">:</span> <span class="token boolean">true</span><span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token function">setTimeout<span class="token punctuation">(</span></span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">=</span><span class="token operator">&gt;</span> <span class="token punctuation">{</span>
     <span class="token comment" spellcheck="true"> // prepend 10 items
</span>      const rowData <span class="token operator">=</span> Array<span class="token punctuation">.</span><span class="token function">from<span class="token punctuation">(</span></span><span class="token keyword">new</span> <span class="token class-name">Array</span><span class="token punctuation">(</span><span class="token number">10</span><span class="token punctuation">)</span><span class="token punctuation">)</span>
      <span class="token punctuation">.</span><span class="token function">map<span class="token punctuation">(</span></span><span class="token punctuation">(</span>val<span class="token punctuation">,</span> i<span class="token punctuation">)</span> <span class="token operator">=</span><span class="token operator">&gt;</span> <span class="token punctuation">(</span><span class="token punctuation">{</span>
        text<span class="token punctuation">:</span> <span class="token string">'Loaded row '</span> <span class="token operator">+</span> <span class="token punctuation">(</span><span class="token operator">+</span><span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>loaded <span class="token operator">+</span> i<span class="token punctuation">)</span><span class="token punctuation">,</span>
        clicks<span class="token punctuation">:</span> <span class="token number">0</span><span class="token punctuation">,</span>
      <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">)</span>
      <span class="token punctuation">.</span><span class="token function">concat<span class="token punctuation">(</span></span><span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>rowData<span class="token punctuation">)</span><span class="token punctuation">;</span>

      <span class="token keyword">this</span><span class="token punctuation">.</span><span class="token function">setState<span class="token punctuation">(</span></span><span class="token punctuation">{</span>
        loaded<span class="token punctuation">:</span> <span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>loaded <span class="token operator">+</span> <span class="token number">10</span><span class="token punctuation">,</span>
        isRefreshing<span class="token punctuation">:</span> <span class="token boolean">false</span><span class="token punctuation">,</span>
        rowData<span class="token punctuation">:</span> rowData<span class="token punctuation">,</span>
      <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span><span class="token punctuation">,</span> <span class="token number">5000</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>

module<span class="token punctuation">.</span>exports <span class="token operator">=</span> RefreshControlExample<span class="token punctuation">;</span></div><div class="embedded-simulator"><p><a class="modal-button-open"><strong>Run this example</strong></a></p><div class="modal-button-open modal-button-open-img"><img alt="Run example in simulator" width="170" height="356" src="img/uiexplorer_main_ios.png"></div><div><div class="modal"><div class="modal-content"><button class="modal-button-close">×</button><div class="center"><iframe class="simulator" src="https://appetize.io/embed/7vdfm9h3e6vuf4gfdm7r5rgc48?device=iphone6s&amp;scale=60&amp;autoplay=false&amp;orientation=portrait&amp;deviceColor=white&amp;params=%7B%22route%22%3A%22RefreshControl%22%7D" width="256" height="550" scrolling="no"></iframe><p>Powered by <a target="_blank" href="https://appetize.io">appetize.io</a></p></div></div></div><div class="modal-backdrop"></div></div></div></div></div></div><div class="docs-prevnext"><a class="docs-prev" href="docs/progressviewios.html#content">← Prev</a><a class="docs-next" href="docs/scrollview.html#content">Next →</a></div>