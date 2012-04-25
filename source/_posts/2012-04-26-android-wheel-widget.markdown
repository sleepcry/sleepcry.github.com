---
layout: post
title: "Android Wheel Widget"
date: 2012-04-26 03:27
comments: true
sharing: true
categories: 
---
A awesome widget to suggest: **WheelView**

open source code available in:[here](http://code.google.com/p/android-wheel/)

How does it looks like?   
![example1](http://2.bp.blogspot.com/_6ZWsj8oW5ek/TUHLiQLNzmI/AAAAAAAADPo/0SKjryIlEJg/s1600/android\-wheel\-cities.png)   
![example2](http://4.bp.blogspot.com/_6ZWsj8oW5ek/TUHMCvNNxcI/AAAAAAAADPs/zdO\_6BsXJKc/s1600/android\-wheel\-time.png)   
![example3](http://2.bp.blogspot.com/_6ZWsj8oW5ek/TUHMwrEYkAI/AAAAAAAADPw/9W9X\-HocKts/s1600/android\-wheel\-slot-machine.png)   

(All these picture above are from google code!)

It is really very easy to use!
Here is an example:

{% codeblock lang:java %}
    WheelView wv; //declaration
    wv = (WheelView) findViewById(R.id.wv1);
    wv.setVisibleItems(5);
    wv.setViewAdapter(new WVAdapter());

    private class WVAdapter extends AbstractWheelAdapter {
        ArrayList<Integer> data;

        public WVAdapter() {
            data=new ArrayList<Integer>();
            data.add(1);
            data.add(2);
            data.add(3);
            data.add(4);
            data.add(12);
        }

        public View getItem(int index, View convertView, ViewGroup parent) {
            LinearLayout ll;
            if (convertView == null) {
                convertView.setText(data.get(index));
            } else {
                TextView tv = new TextView(getContext());
                tv.setText(data.get(index));
                return tv;
            }
        }

        @Override
        public int getItemsCount() {
            return data == null ? 0 : data.size();
        }


    }
{% endcodeblock %}
