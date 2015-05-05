关于日期和时间,相关类如下
java.util.Date
java.util.TimeZone
java.text.DateFormat
java.text.SimpleDateFormat

Date、String、Timestamp之间没找到好的转换方法,下面两个先用着,以后再具体研究

<pre>
public long stringToTimestamp(String string) {
	java.text.SimpleDateFormat simpleDateFormat = new java.text.SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
	java.util.Date date = null;
	try {
		date = simpleDateFormat.parse(string);
	} catch (java.text.ParseException e) {
		e.printStackTrace();
	}
	return (date != null) ? date.getTime() / 1000 : -1;
}
</pre>

<pre>
public String timestampToString(long timestamp) {
	java.text.SimpleDateFormat simpleDateFormat = new java.text.SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
	java.util.Date date = new java.util.Date(timestamp * 1000L);
	return simpleDateFormat.format(date);
}
</pre>