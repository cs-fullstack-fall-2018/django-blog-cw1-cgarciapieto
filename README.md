# django-blog-cw1

Add edit blog post support to the blog project.

def post_edit(request, pk):
    theentry = get_object_or_404(Post, pk=pk)
    if request.method == "POST":
        form = PostForm(request.POST,instance=theentry)


    else:
        form = PostForm(instance=theentry)
    return render(request, 'blog_app/post_edit.html', {'form':form})
