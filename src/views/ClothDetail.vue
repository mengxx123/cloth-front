<template>
    <my-page title="标准尺码对照表" backable>
        <section class="tool-box" v-if="type !== 6 && type !== 25 && type !== 41">
            <div class="tool-box-body">
                <div class="form-horizontal">
                    <!-- <div class="form-group">
                        <label class="control-label col-sm-3">类型：</label>
                        <div class="col-sm-9">
                            <select id="type" class="form-control">
                                <optgroup label="女装">
                                    <option value="1">女装</option>
                                    <option value="2">衬衫</option>
                                    <option value="3">连衣裙</option>
                                    <option value="4">裤子</option>
                                    <option value="5">文胸</option>
                                    <option value="6">内裤</option>
                                </optgroup>
                                <optgroup label="男装">
                                    <option value="21">男装</option>
                                    <option value="22">衬衫</option>
                                    <option value="23">西装</option>
                                    <option value="24">裤子</option>
                                    <option value="25">内裤</option>
                                </optgroup>
                                <optgroup label="童装">
                                    <option value="31">童装</option>
                                    <option value="32">婴童</option>
                                    <option value="33">中童</option>
                                    <option value="34">大童</option>
                                </optgroup>
                                <optgroup label="其他">
                                    <option value="41">鞋码</option>
                                </optgroup>
                            </select>
                        </div>
                    </div> -->
                    <div id="form">
                        <div class="form-group">
                            <ui-text-field v-model.number="height" type="number" label="身高（厘米）" /> 
                        </div>
                        <div class="form-group">
                            <ui-text-field v-model.number="weight" type="number" label="体重（斤）" /> 
                        </div>
                        <div class="form-group">
                            <ui-raised-button label="尺码生成" primary @click="ok" />
                        </div>
                    </div>
                    <div class="result">{{ result }}</div>
                </div>
            </div>
        </section>
        <div class="size_right">
            <div v-if="type === 1">
                <ui-article>
                    <h2 class="title">女装标准尺码对照表</h2>
                    <table class="table table-bordered">
                        <tr><td>上衣尺码</td><td>S</td><td>M</td><td>L</td><td>XL</td><td>XXL</td><td>XXXL</td></tr>
                        <tr><td>服装尺码</td><td>36</td><td>38</td><td>40</td><td>42</td><td>44</td><td>46</td></tr>
                        <tr><td>胸 围/cm</td><td>79-82</td><td>83-86</td><td>87-90</td><td>91-94</td><td>95-98</td><td>99-103</td></tr>
                        <tr><td>腰 围/cm</td><td>62-66</td><td>67-70</td><td>71-74</td><td>75-78</td><td>79-82</td><td>83-86</td></tr>
                        <tr><td>肩 宽/cm</td><td>37</td><td>38</td><td>39</td><td>40</td><td>41</td><td>42</td></tr>
                        <tr><td>身高/胸围</td><td>155/82A</td><td>160/86A</td><td>165/90A</td><td>170/94A</td><td>172/98A</td><td>175/102A</td></tr>
                    </table>
                    <article class="article">
                        <p>说明：</p>
                        <p>上述提供的计算公式是根据经验得到的数据参数，试用于绝大多数人群，不适用于特殊体型要求。</p>
                        <p>国内比较普遍的一个判断胖瘦的公式是：</p>
                        <p>女性之标准体重（千克）＝身长（厘米）－102</p>
                        <p>注意：身高体重与尺寸没有绝对的关系，155CM丰腴和168CM瘦高的女生也许会穿同一个尺寸。胸围是影响上衣尺寸选择的关键因素，建议你可以以胸围选择。</p>
                    </article>
                </ui-article>
            </div>
            <div v-if="type === 2">
                <ui-article>
                    <h2 class="title">女衬衫标准尺码对照表</h2>
                    <table class="table table-bordered">
                        <tr><td>衬衫尺码</td><td>S</td><td>M</td><td>L</td><td>XL</td><td>XXL</td><td>XXXL</td></tr>
                        <tr><td>国际尺码</td><td>36</td><td>37</td><td>38</td><td>39</td><td>40</td><td>41</td></tr>
                        <tr><td>胸 围/cm</td><td>79-82</td><td>83-86</td><td>87-90</td><td>91-94</td><td>95-98</td><td>99-103</td></tr>
                        <tr><td>腰 围/cm</td><td>62-66</td><td>67-70</td><td>71-74</td><td>75-78</td><td>79-82</td><td>83-86</td></tr>
                        <tr><td>肩 宽/cm</td><td>37</td><td>38</td><td>39</td><td>40</td><td>41</td><td>42</td></tr>
                        <tr><td>身高/胸围</td><td>155/82A</td><td>160/86A</td><td>165/90A</td><td>170/94A</td><td>172/98A</td><td>175/102A</td></tr>
                    </table>
                    <p>国家服装号型的含义 号型定义：</p>
                    <p>"号"指人体的身高，以cm为单位，是设计和选购服装长短的依据；"型"指人体的胸围和腰围，以cm为单位，是设计和选购服装肥瘦的依据。体型分类：以人体的胸围与腰围的差数为依据来划分体型，并将体型分为四类，体型分类代号分别为Y(偏瘦)、A（正常）、B（偏胖）、C（肥胖）</p>
                </ui-article>
            </div>
            <div v-if="type === 3">
                <ui-article>
                    <h2 class="title">连衣裙尺码对照表</h2>
                    <table class="table table-bordered">
                        <tr><td>裙子尺码</td><td>S</td><td>M</td><td>L</td><td>XL</td><td>XXL</td></tr>
                        <tr><td>服装尺码</td><td>36</td><td>38</td><td>40</td><td>42</td><td>44</td></tr>
                        <tr><td>胸 围/cm</td><td>79-82</td><td>83-86</td><td>87-90</td><td>91-94</td><td>95-98</td></tr>
                        <tr><td>腰 围/cm</td><td>62-66</td><td>67-70</td><td>71-74</td><td>75-78</td><td>79-82</td></tr>
                        <tr><td>肩 宽/cm</td><td>37</td><td>38</td><td>39</td><td>40</td><td>41</td></tr>
                        <tr><td>身高/胸围</td><td>155/82A</td><td>160/86A</td><td>165/90A</td><td>170/94A</td><td>172/98A</td></tr>
                    </table>
                    <h3>服装号型标志：</h3>
                    <p>号型的表示方法为号与型之间用斜线分开，后接体型分类代号。例如：上装160/84A，其中160为身高，代表号，84为胸围，代表型，A代表体型代号；下装160/68A，其中160为身高，代表号，68为腰围，代表型，A代表体型代号。</p>
                </ui-article>
            </div>
            <div v-if="type === 4">
                <ui-article>
                    <h2 class="title">女裤子尺码对照表</h2>
                    <table class="table table-bordered">
                        <tr><td>女裤</td><td colspan="2">S</td><td colspan="2">M</td><td colspan="2">L</td><td colspan="2">XL</td></tr>
                        <tr><td>裤子尺码(英寸)</td><td>25</td><td>26</td><td>27</td><td>28</td><td>29</td><td>30</td><td>31</td><td>32</td></tr>
                        <tr><td>国标号型</td><td>155/62A</td><td>159/64A</td><td>160/66A</td><td>164/68A</td><td>165/70A</td><td>169/72A</td><td>170/74A</td><td>170/76A</td></tr>
                        <tr><td>对应臀围(cm)</td><td>85</td><td>87.5</td><td>90</td><td>92.5</td><td>95</td><td>97.5</td><td>100</td><td>102.5</td></tr>
                        <tr><td>对应腰围(cm)</td><td>62</td><td>64.5</td><td>67</td><td>69.5</td><td>72</td><td>74.5</td><td>77</td><td>79.5</td></tr>
                    </table>
                    <h3>说明：</h3>
                    <p>如何测量裤侧长：从腰部开始测量一直到脚裸的长度就是裤侧长。</p>
                    <p>如何测量腰围：经脐点(om)的腰部水平围长</p>
                    <p>标准腰围计算方法：腰围=身高的1/2减19厘米(如:身高160cm的标准腰围=160cm /2-19=61cm )</p>
                </ui-article>
            </div>
            <div v-if="type === 5">
                <ui-article>
                    <h2 class="title">文胸尺码对照表</h2>
                    <table class="table table-bordered">
                        <tr><td>下胸围(cm)</td><td>上胸围(cm)</td><td>国际尺码</td><td>下胸围(cm)</td><td>上胸围(cm)</td><td>国际尺码</td></tr>
                        <tr><td rowspan="5">68-72</td><td>80</td><td>32/70A</td><td rowspan="5">73-77</td><td>85</td><td>34/75A</td></tr>
                        <tr><td>83</td><td>32/70B</td><td>88</td><td>34/75B</td></tr>
                        <tr><td>85</td><td>32/70C</td><td>90</td><td>34/75C</td></tr>
                        <tr><td>88</td><td>32/70D</td><td>95</td><td>34/75D</td></tr>
                        <tr><td>&nbsp;</td><td>&nbsp;</td><td>98</td><td>34/75E</td></tr>
                        <tr><td>下胸围(cm)</td><td>上胸围(cm)</td><td>国际尺码</td><td>下胸围(cm)</td><td>上胸围(cm)</td><td>国际尺码</td></tr>
                        <tr><td rowspan="5">78-82</td><td>90</td><td>36/80A</td><td rowspan="5">83-87</td><td>95-97</td><td>38/85A</td></tr>
                        <tr><td>93</td><td>36/80B</td><td>99-101</td><td>38/85B</td></tr>
                        <tr><td>95</td><td>36/80C</td><td>101-103</td><td>38/85C</td></tr>
                        <tr><td>98</td><td>36/80D</td><td>103-105</td><td>338/85D</td></tr>
                        <tr><td>103</td><td>36/80E</td><td>&nbsp;</td><td>&nbsp;</td></tr>
                        <tr><td>下胸围(cm)</td><td>上胸围(cm)</td><td>国际尺码</td><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td></tr>
                        <tr><td rowspan="4">88-92</td><td>103</td><td>40/90B</td><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td></tr>
                        <tr><td>105</td><td>40/90C</td><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td></tr>
                        <tr><td>108</td><td>40/90D</td><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td></tr>
                        <tr><td>113</td><td>40/90E</td><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td></tr>
                    </table>
                </ui-article>
            </div>
            <div v-if="type === 6">
                <ui-article>
                    <h2 class="title">女式内裤尺码表</h2>
                    <table class="table table-bordered">
                        <tr><td>尺码</td><td>S</td><td>M</td><td>L</td><td>XL</td></tr>
                        <tr><td>腰围</td><td>55-61</td><td>61-67</td><td>67-73</td><td>73-79</td></tr>
                        <tr><td>腰围（市尺）</td><td>1.8-1.9</td><td>1.9-2.1</td><td>2.1-2.2</td><td>2.2-2.3</td></tr>
                        <tr><td>臀围</td><td>80-86</td><td>85-93</td><td>90-98</td><td>95-103</td></tr>
                    </table>
                    <h3>备注：</h3>
                    <p>按贴身腰围为准。相同码数，但因款式不同、材料不同等因素，会有2cm左右偏差，购买时最好咨询相关人员为准。</p>
                </ui-article>
            </div>

            <div v-if="type === 21">
                <ui-article>
                    <h2 class="title">男装标准尺码对照表</h2>
                    <table class="table table-bordered table-responce">
                        <tr>
                            <td>上衣尺码</td>
                            <td>S</td>
                            <td>M</td>
                            <td>L</td>
                            <td>XL</td>
                            <td>XXL</td>
                            <td>XXXL</td>
                        </tr>
                        <tr>
                            <td>服装尺码</td>
                            <td>46</td>
                            <td>48</td>
                            <td>50</td>
                            <td>52</td>
                            <td>54</td>
                            <td>56</td>
                        </tr>
                        <tr>
                            <td>中国号型</td>
                            <td>165/80A</td>
                            <td>170/84A</td>
                            <td>175/88A</td>
                            <td>180/92A</td>
                            <td>185/96A</td>
                            <td>190/100A</td>
                        </tr>
                        <tr>
                            <td>胸 围/cm</td>
                            <td>82-85</td>
                            <td>86-89</td>
                            <td>90-93</td>
                            <td>94-97</td>
                            <td>98-102</td>
                            <td>103-107</td>
                        </tr>
                        <tr>
                            <td>腰 围/cm</td>
                            <td>72-75</td>
                            <td>76-79</td>
                            <td>80-84</td>
                            <td>85-88</td>
                            <td>89-92</td>
                            <td>93-96</td>
                        </tr>
                        <tr>
                            <td>肩 宽/cm</td>
                            <td>42</td>
                            <td>44</td>
                            <td>46</td>
                            <td>48</td>
                            <td>50</td>
                            <td>52</td>
                        </tr>
                        <tr>
                            <td>适合身高/cm</td>
                            <td>163/167</td>
                            <td>168/172</td>
                            <td>173/177</td>
                            <td>178/182</td>
                            <td>182/187</td>
                            <td>187/190</td>
                        </tr>
                    </table>
                    <h3>说明：</h3>
                    <p>上述提供的计算公式是根据经验得到的数据参数，试用于绝大多数人群，不适用于特殊体型要求。</p>
                    <p>国内比较普遍的一个判断胖瘦的公式是：</p>
                    <p>男性标准体重：身高（厘米）－105= 标准体重（千克）</p>
                </ui-article>
            </div>
            <div v-if="type === 22">
                <ui-article>
                    <h2 class="title">衬衫尺码对照表</h2>
                    <table class="table table-bordered">
                        <tr><td>衬衫尺码</td><td>37</td><td>38</td><td>39</td><td>40</td><td>41</td><td>42</td><td>43</td></tr>
                        <tr><td>国际型号</td><td>160/80A</td><td>165/84A</td><td>170/88A</td><td>175/92A</td><td>180/96A</td><td>180/100A</td><td>185/104A</td></tr>
                        <tr><td>肩宽</td><td>42-43</td><td>44-45</td><td>46-47</td><td>47-48</td><td>49-50</td><td>51-52</td><td>53-54</td></tr>
                        <tr><td>胸围</td><td>98-101</td><td>102-105</td><td>106-109</td><td>110-113</td><td>114-117</td><td>118-121</td><td>122-125</td></tr>
                        <tr><td>衣长</td><td>72</td><td>74</td><td>76</td><td>78</td><td>80</td><td>82</td><td>83</td></tr>
                        <tr><td>身高</td><td>160</td><td>165</td><td>170</td><td>175</td><td>180</td><td>185</td><td>190</td></tr>
                        <tr><td>上衣尺码</td><td>XS</td><td>S</td><td>M</td><td>L</td><td>XL</td><td>XXL</td><td>XXXL</td></tr>
                    </table>
                    <h3>注意：</h3>
                    <p>男式西服按照男士体型可分为偏瘦型、标准型、偏胖型。但这只是标准尺码，实际生活中因个人体型差异较大。</p>
                </ui-article>
            </div>
            <div v-if="type === 23">
                <ui-article>
                    <h2 class="title">西装尺码对照表</h2>
                    <table class="table table-bordered">
                        <tbody><tr><td>尺    码</td><td>规    格</td><td>板    型</td><td>衣    长</td><td>胸    围</td><td>肩    宽</td><td>袖    长</td></tr>
                        <tr><td>2R48</td><td>165/96C</td><td>偏胖</td><td>70</td><td>106</td><td>44.7</td><td>60</td></tr>
                        <tr><td>2R50</td><td>170/100C</td><td>偏胖</td><td>72</td><td>110</td><td>45.9</td><td>61.5</td></tr>
                        <tr><td>2R52</td><td>175/104C</td><td>偏胖</td><td>74</td><td>114</td><td>47.1</td><td>63</td></tr>
                        <tr><td>2R54</td><td>180/108C</td><td>偏胖</td><td>76</td><td>118</td><td>48.3</td><td>64.5</td></tr>
                        <tr><td>2R56</td><td>185/112C</td><td>偏胖</td><td>78</td><td>122</td><td>49.5</td><td>66</td></tr>
                        <tr><td>4R46</td><td>165/92B</td><td>标准</td><td>70</td><td>102</td><td>43.5</td><td>60</td></tr>
                        <tr><td>4R48</td><td>170/96B</td><td>标准</td><td>72</td><td>106</td><td>44.7</td><td>61.5</td></tr>
                        <tr><td>4R50</td><td>175/100B</td><td>标准</td><td>74</td><td>110</td><td>45.9</td><td>63</td></tr>
                        <tr><td>4R52</td><td>180/104B</td><td>标准</td><td>76</td><td>114</td><td>47.1</td><td>64.5</td></tr>
                        <tr><td>4R54</td><td>185/108B</td><td>标准</td><td>78</td><td>118</td><td>48.3</td><td>66</td></tr>
                        <tr><td>6R44</td><td>165/88A</td><td>偏瘦</td><td>70</td><td>98</td><td>42.3</td><td>60</td></tr>
                        <tr><td>6R46</td><td>170/92A</td><td>偏瘦</td><td>72</td><td>102</td><td>43.5</td><td>61.5</td></tr>
                        <tr><td>6R48</td><td>175/96A</td><td>偏瘦</td><td>74</td><td>106</td><td>44.7</td><td>63</td></tr>
                        <tr><td>6R50</td><td>180/100A</td><td>偏瘦</td><td>76</td><td>110</td><td>45.9</td><td>64.5</td></tr>
                        <tr><td>6R52</td><td>185/104A</td><td>偏瘦</td><td>78</td><td>114</td><td>47.1</td><td>66</td></tr>
                        </tbody></table>
                    <p>男式西服按照男士体型可分为偏瘦型、标准型、偏胖型</p>
                </ui-article>
            </div>
            <div v-if="type === 24">
                <ui-article>
                    <h2 class="title">男裤子尺码对照表</h2>
                    <table class="table table-bordered">
                        <tr><td rowspan="2">男裤子尺码</td><td colspan="2">S</td><td colspan="2">M</td><td colspan="2">L</td></tr>
                        <tr><td>170/72A</td><td>170/74A</td><td>170/76A</td><td>175/80A</td><td>175/82A</td><td>175/84A</td></tr>
                        <tr><td>裤子尺码(英寸)</td><td>29</td><td>30</td><td>31</td><td>32</td><td>33</td><td>34</td></tr>
                        <tr><td>对应臀围(cm)</td><td>97.5</td><td>100</td><td>102.5</td><td>105</td><td>107.5</td><td>110</td></tr>
                        <tr><td>对应腰围(cm)</td><td>73.7</td><td>76.2</td><td>78.7</td><td>81.3</td><td>83.8</td><td>86.4</td></tr>
                        <tr><td>腰围/市尺</td><td>2尺2寸</td><td>2尺3寸</td><td>2尺4寸</td><td>2尺4寸</td><td>2尺5寸</td><td>2尺6寸</td></tr>
                    </table>
                    <table class="table table-bordered">
                        <tr><td rowspan="2">男裤子尺码</td><td colspan="2">XL</td><td colspan="2">XXL</td><td colspan="2">XXXL</td></tr>
                        <tr><td>180/86A</td><td>180/90A</td><td>185/92A</td><td>185/94B</td><td>190/98B</td><td>195/102B</td></tr>
                        <tr><td>裤子尺码(英寸)</td><td>35</td><td>36</td><td>37</td><td>38</td><td>40</td><td>42</td></tr>
                        <tr><td>对应臀围(cm)</td><td>112.5</td><td>100</td><td>117.5</td><td>120</td><td>122.5</td><td>130</td></tr>
                        <tr><td>对应腰围(cm)</td><td>89</td><td>91.4</td><td>93.3</td><td>96.5</td><td>101.6</td><td>106.6</td></tr>
                        <tr><td>腰围/市尺</td><td>2尺6寸</td><td>2尺7寸</td><td>2尺8寸</td><td>2尺9寸</td><td>3尺1寸</td><td>3尺2寸</td></tr>
                    </table>
                </ui-article>
            </div>
            <div v-if="type === 25">
                <ui-article>
                    <h2 class="title">男式内裤尺码表</h2>
                    <table class="table table-bordered">
                        <tr><td>尺码</td><td>M</td><td>L</td><td>XL</td><td>XXL</td></tr>
                        <tr><td>腰围</td><td>62-70</td><td>66-74</td><td>72-82</td><td>76-84</td></tr>
                        <tr><td>腰围（市尺）</td><td>2.0-2.2</td><td>2.2-2.4</td><td>2.4-2.5</td><td>>2.6</td></tr>
                        <tr><td>臀围</td><td>82-90</td><td>86-94</td><td>88-96</td><td>94-102</td></tr>
                        <tr><td>身高</td><td>160-170</td><td>165-175</td><td>170-180</td><td>175-185</td></tr>
                    </table>
                    <p>备注：</p>
                    <p>按贴身腰围为准。相同码数，但因款式不同、材料不同等因素，会有2cm左右偏差，购买时最好咨询相关人员为准。</p>
                </ui-article>
            </div>

            <div v-if="type === 31">
                <ui-article>
                    <h2 class="title">童装尺码对照表</h2>
                    <table class="table table-bordered">
                        <tbody><tr><td>年龄</td><td>尺码</td><td>身高</td><td>胸围</td><td>腰围</td></tr>
                        <tr><td>0-3个月</td><td>59</td><td>59</td><td>50</td><td>38</td></tr>
                        <tr><td>3-6个月</td><td>66</td><td>66</td><td>53</td><td>40</td></tr>
                        <tr><td>6-9个月</td><td>73</td><td>73</td><td>56</td><td>42</td></tr>
                        <tr><td>9-12个月</td><td>80</td><td>80</td><td>59</td><td>44</td></tr>
                        <tr><td>1-1.5岁</td><td>90</td><td>90</td><td>62</td><td>46</td></tr>
                        <tr><td>1.5岁-3岁</td><td>100</td><td>100</td><td>54</td><td>52</td></tr>
                        <tr><td>3岁-6岁</td><td>110</td><td>110</td><td>58</td><td>54</td></tr>
                        <tr><td>6岁-8岁</td><td>120</td><td>120</td><td>64</td><td>56</td></tr>
                        <tr><td>8岁-10岁</td><td>130</td><td>130</td><td>65</td><td>58</td></tr>
                        <tr><td>10岁-11岁</td><td>140</td><td>150</td><td>68</td><td>60</td></tr>
                        <tr><td>12岁-13岁</td><td>150</td><td>150</td><td>72</td><td>62</td></tr>
                        <tr><td>14岁-15岁</td><td>160</td><td>160</td><td>76</td><td>64</td></tr>
                        </tbody>
                    </table>
                    <div class="p">说明：<br />上述提供的计算公式是根据经验得到的数据参数，试用于绝大多数人群，不适用于特殊体型要求。注意：表格中尺码项即为小孩身高，请顾客按照尺码项选择合适的码数，宝贝幼嫩肌肤。</div>
                </ui-article>
            </div>
            <div v-if="type === 32">
                <ui-article>
                    <h2 class="title">婴童尺码对照表</h2>
                    <table class="table table-bordered">
                        <tr><td>尺码(cm)</td><td>59</td><td>66</td><td>73</td><td>80</td><td>90</td></tr>
                        <tr><td>年龄</td><td>0-3个月</td><td>3-6个月</td><td>6-9个月</td><td>9-12个月</td><td>1-1.5岁</td></tr>
                        <tr><td>身高</td><td>59</td><td>66</td><td>73</td><td>80</td><td>90</td></tr>
                        <tr><td>胸围</td><td>41</td><td>44</td><td>47</td><td>50</td><td>52</td></tr>
                        <tr><td>腰围</td><td>38</td><td>40</td><td>42</td><td>44</td><td>46</td></tr>
                    </table>
                    <div class="p">说明：<br/>上述提供的计算公式是根据经验得到的数据参数，试用于绝大多数人群，不适用于特殊体型要求。<br />注意：表格中尺码项即为小孩身高，请顾客按照尺码项选择合适的码数。宝贝幼嫩肌肤，需要用心呵护。童装与成人服饰最大的区别在于用料和印染技术，宝耶童装精选上等环保面料，采用最新最环保的印染技术，保证毎一件衣服都对宝贝的皮肤无任何刺激。</div>
                </ui-article>
            </div>
            <div v-if="type === 33">
                <ui-article>
                    <h2 class="title">中童尺码对照表</h2>
                    <table class="table table-bordered">
                        <tr><td>尺码(cm)</td><td>100</td><td>110</td><td>120</td><td>130</td></tr>
                        <tr><td>年龄</td><td>1.5岁-3岁</td><td>3岁-6岁</td><td>6岁-8岁</td><td>8岁-10岁</td></tr>
                        <tr><td>身高</td><td>100</td><td>110</td><td>120</td><td>130</td></tr>
                        <tr><td>胸围</td><td>54</td><td>58</td><td>62</td><td>66</td></tr>
                        <tr><td>腰围</td><td>52</td><td>54</td><td>56</td><td>58</td></tr>
                    </table>
                    <div class="p">说明：<br/>上述提供的计算公式是根据经验得到的数据参数，试用于绝大多数人群，不适用于特殊体型要求。<br/>注意：表格中尺码项即为小孩身高，请顾客按照尺码项选择合适的码数。<br/>吊牌上的执行标准的含义：<br/>A类，B类，C类的含义：这是国标中对甲醛含量的规定，A类是婴糼儿用品，B类是直接接触皮肤，C类是非直接接触皮肤。</div>
                </ui-article>
            </div>
            <div v-if="type === 34">
                <ui-article>
                    <h2 class="title">大童尺码对照表</h2>
                    <table class="table table-bordered">
                        <tr><td>尺码(cm)</td><td>130</td><td>140</td><td>150</td><td>160</td></tr>
                        <tr><td>年龄</td><td>8岁-10岁</td><td>10岁-11岁</td><td>12岁-13岁</td><td>14岁-15岁</td></tr>
                        <tr><td>身高</td><td>130</td><td>140</td><td>150</td><td>160</td></tr>
                        <tr><td>胸围</td><td>66</td><td>69</td><td>73</td><td>78</td></tr>
                        <tr><td>腰围</td><td>58</td><td>60</td><td>62</td><td>64</td></tr>
                    </table>
                    <div class="p">说明：<br/>上述提供的计算公式是根据经验得到的数据参数，试用于绝大多数人群，不适用于特殊体型要求。<br/>注意：表格中尺码项即为小孩身高，请顾客按照尺码项选择合适的码数。<br/>宝贝幼嫩肌肤，需要用心呵护。童装与成人服饰最大的区别在于用料和印染技术，宝耶童装精选上等环保面料，采用最新最环保的印染技术，保证毎一件衣服都对宝贝的皮肤无任何刺激。</div>
                </ui-article>
            </div>

            <div v-if="type === 41">
                <ui-article>
                    <h2 class="title">男鞋尺码表</h2>
                    <table class="table table-bordered">
                        <tr><td>脚长 cm</td><td>24.5</td><td>25</td><td>25.5</td><td>26</td><td>26.5</td><td>27</td><td>27.5</td><td>28</td></tr>
                        <tr><td>欧洲EUR</td><td>39 1/3</td><td>40</td><td>40 2/3</td><td>41 1/3</td><td>42</td><td>42 2/3</td><td>43 1/3</td><td>44</td></tr>
                        <tr><td>美国 US</td><td>6.5</td><td>7</td><td>7.5</td><td>8</td><td>8.5</td><td>9</td><td>9.5</td><td>10</td></tr>
                        <tr><td>英国 UK</td><td>6</td><td>6.5</td><td>7</td><td>7.5</td><td>8</td><td>8.5</td><td>9</td><td>9.5</td></tr>
                    </table>

                    <h2 class="title">女鞋尺码表</h2>
                    <table class="table table-bordered">
                        <tr><td>脚长 cm</td><td>22.5</td><td>23</td><td>23.5</td><td>24</td><td>24.5</td><td>25</td><td>25.5</td><td>26</td></tr>
                        <tr><td>欧洲EUR</td><td>36 2/3</td><td>37 1/3</td><td>38</td><td>38 2/3</td><td>39 1/3</td><td>40</td><td>40 2/3</td><td>41 1/3</td></tr>
                        <tr><td>美国 US</td><td>5.5</td><td>6</td><td>6.5</td><td>7</td><td>7.5</td><td>8</td><td>8.5</td><td>9</td></tr>
                        <tr><td>英国 UK</td><td>4.5</td><td>5</td><td>5.5</td><td>6</td><td>6.5</td><td>7</td><td>7.5</td><td>8</td></tr>
                    </table>
                    <div class="p">选购时请综合参考尺码表中的各项参数，这有助您选择到更好的尺码。<br />(仅供参考，测量脚时请注意用适当力度轻踩水平面上。因测量方法不同，测量出来的数据也会不一样。)<br />国际标准鞋号表示的是脚长的毫米数。中国标准采用毫米数或厘米数。如：245是毫米数，24 1/2是厘米数，表示一样的尺码。</div>
                </ui-article>
            </div>
        </div>
    </my-page>
</template>

<script>
    /* eslint-disable */
    export default {
        data () {
            return {
                type: null,
                height: null,
                weight: null,
                result: ''
            }
        },
        mounted() {
            this.type = parseInt(this.$route.params.type)
            let type = this.type
        },
        methods: {
            ok() {
                if (!this.height) {
                    this.$message({
                        type: 'danger',
                        text: '请输入身高'
                    })
                    return
                }
                if (this.height < 100 || this.height > 200) {
                    this.$message({
                        type: 'danger',
                        text: '身高输入有误，请重新输入'
                    })
                    return
                }
                if (!this.weight) {
                    this.$message({
                        type: 'danger',
                        text: '请输入体重'
                    })
                    return
                }
                this.result = this.calSize(this.height, this.weight, this.type)
            },
            calSize(height, wight, ci) {
                console.log('计算', height, wight, ci)

                //ci:1-4 女装  ci:21-24 男装  ci:11-14 童装 ci:15 文胸
                var size;
                var sarr = new Array();
                if (ci >= 1 && ci <= 4) {
                    //1-S,2-M,3-L,4-XS,5-XL,6-XXL
                    sarr = ["S", 80, 99, 145, 149, "S", 90, 99, 150, 169, "S", 80, 89, 160, 169, "M", 80, 99, 170, 172, "M", 90, 99, 173, 175, "M", 100, 109, 145, 149, "M", 100, 109, 155, 179, "L", 110, 119, 145, 149, "L", 110, 119, 155, 179, "L", 120, 129, 155, 159, "L", 120, 129, 170, 179, "XS", 80, 89, 150, 159, "XL", 110, 119, 150, 154, "XL", 120, 129, 145, 154, "XL", 120, 129, 160, 169, "XL", 130, 139, 160, 179, "XL", 140, 149, 173, 179, "XXL", 130, 139, 150, 159, "XXL", 140, 149, 155, 172];

                }
                else if (ci <= 24) {
                    sarr = [44,85,115,153,163,44,85,105,163,168,44,85,95,168,173,46,115,135,153,163,46,135,145,153,158,46,105,125,163,168,46,95,115,168,173,46,95,105,173,178,48,145,165,153,158,48,135,155,158,163,48,125,145,163,168,48,115,145,168,173,48,105,125,173,178,48,105,115,178,183,50,165,185,153,158,50,155,175,158,163,50,145,165,163,168,50,145,155,168,173,50,125,155,173,178,50,115,135,178,183,50,115,125,183,188,52,175,195,158,163,52,165,185,163,168,52,155,175,168,173,52,155,165,173,183,52,135,155,178,183,52,125,145,183,188,52,125,135,188,193,54,185,195,163,173,54,175,185,168,178,54,165,175,173,188,54,145,165,183,188,54,135,155,188,193,56,195,215,168,183,56,185,195,173,193,56,175,185,178,193,56,155,175,188,193,58,195,215,183,193];

                }
                else if (ci <= 34) {
                    sarr = [59, 6, 11, 55, 62,66,12,14,55,62,66,8,16,63,69,73,17,20,63,69,73,12,20,70,76,80,21,24,70,76,80,16,24,77,83,90,23,28,77,83,90,20,30,84,94,100,31,36,84,94,100,22,38,95,104,110,39,44,95,104,110,26,42,105,114,120,43,52,105,114,120,34,52,115,124,130,53,60,115,124,130,40,60,125,134,140,61,80,125,134,140,52,76,135,144,150,77,90,135,144,150,70,84,145,154,160,85,100,145,154,160,80,110,155,164,165,111,130,155,164];
                }
                else if (ci == 5) {
                    sarr = ["32/70A",68, 72, 80, 82,  "32/70B", 68, 72,83, 84,  "32/70C", 68, 72,85, 87,  "32/70D", 68, 72,88, 88,  "34/75A",73, 77, 85, 87,  "34/75B", 73, 77,88, 89,  "34/75C",73, 77, 90, 94,  "34/75D",73,77,95,97,"34/75E",73,77,98,98,"36/80A",78,82,90,92,"36/80B",78,82,93,94,"36/80C",78,82,95,97,"36/80D",78,82,98,102,"36/80E",78,82,103,103,"38/85A",83,87,95,97,"38/85B",83,87,99,101,"38/85C",83,87,101,103,"38/85D",83,87,103,105,"40/90B",88,92,103,104,"40/90C",88,92,105,107,"40/90D",88,92,108,112,"40/90E",88,92,113,113];
                }

                for (var i = 0; i < sarr.length / 5; i++) {
                    if (wight >= sarr[5 * i + 1] && wight <= sarr[5 * i + 2] && height >= sarr[5 * i + 3] && height <= sarr[5 * i + 4]) {
                        size = sarr[5 * i];
                        break;
                    }
                    if (i == sarr.length / 5 - 1) {
                        alert("亲！你的身材实在是太棒了，已经超出了普通人的范畴！");
                    }
                }
                if (ci == 4) { //女装裤子
                    switch (size) {
                        case "XS":
                            size = "24/25";
                            break;
                        case "S":
                            size = "25/26";
                            break;
                        case "M":
                            size = "27/28";
                            break;
                        case "L":
                            size = "29/30";
                            break;
                        case "XL":
                            size = "31/32";
                            break;
                        case "XXL":
                            size = "33/34";
                            break;
                    }
                }
                if (ci == 21) { //男装
                    switch (size) {
                        case 44:
                            size = "XS";
                            break;
                        case 46:
                            size = "S";
                            break;
                        case 48:
                            size = "M";
                            break;
                        case 50:
                            size = "L";
                            break;
                        case 52:
                            size = "XL";
                            break;
                        case 54:
                            size = "XXL";
                            break;
                        case 56:
                            size = "XXXL";
                            break;
                    }
                }
                if (ci == 22) { //男衬衫
                    switch (size) {
                        case 44:
                            size = "37";
                            break;
                        case 46:
                            size = "38";
                            break;
                        case 48:
                            size = "39";
                            break;
                        case 50:
                            size = "40";
                            break;
                        case 52:
                            size = "41";
                            break;
                        case 54:
                            size = "42";
                            break;
                        case 56:
                            size = "43";
                            break;
                    }
                }
                if (ci == 24) { //男裤子
                    switch (size) {
                        case 44:
                            size = "27";
                            break;
                        case 46:
                            size = "28/29/30";
                            break;
                        case 48:
                            size = "30/31/32";
                            break;
                        case 50:
                            size = "33/34";
                            break;
                        case 52:
                            size = "35/36";
                            break;
                        case 54:
                            size = "38";
                            break;
                        case 56:
                            size = "40";
                            break;
                    }
                }

                console.log(size)
                return size ;
            }
        }
    }
</script>

<style lang="scss" scoped>
/**/
.tool-box {
    max-width: 480px;
    padding: 16px;
    margin-bottom: 24px;
    background-color: #fff;
    border-radius: 4px;
    padding: 16px;
    box-shadow: 0 1px 6px rgba(0,0,0,.117647), 0 1px 4px rgba(0,0,0,.117647);
    .result {
        margin-top: 16px;
        color: #f60;
        font-weight: bold;
    }
}
</style>
