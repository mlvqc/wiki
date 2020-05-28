# Help 

This file is designed to help with building markdown files. 

### Code blocks 

You can add code blocks in the following way: 

````markdown 

​```language
code goes here
```

````

where language is the name of the programming language that you are putting in the block. There is support for a lot of languages. 
Python (python) and C++ (cpp) are two that we might use often. 

This will be formatted like: 

​```python
def sum(a, b): 
    return a + b

```

### Table of contents 

You can add a table of contents to a page by including the following in the markdown file: 

```markdown
<!-- toc --> 
```

The table of contents is then rendered in that position. You do not need the tocstop part, only gitbooks renders that (unsure why). 


### Hint blocks 

You can add hint blocks: 

```markdown 
{% hint style='info' %}
Important info: this note needs to be highlighted
{% endhint %}
```

There are four styles: info (default), tip, danger, and warning. Examples are below. 


{% hint style='info' %}
This is an info block.
{% endhint %}

{% hint style='tip' %}
This is a tip block.
{% endhint %}

{% hint style='danger' %}
This is a danger block. 
{% endhint %}

{% hint style='warning' %}
This is a warning block.
{% endhint %}

### Including Images

Images can be added and centred by using the syntax

```markdown
<center><img src="IMAGE_RELATIVE_PATH" style="zoom:100%;" /></center>
```

It is important to use a relative path, as an absolute path would be broken when the image is pushed to github.  





