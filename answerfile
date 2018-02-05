import glob, json

def compareFiles(path):
    files = glob.glob(path+"*")
    output = []
    output.append([files[0].split("\\")[-1]])
    flag = False
    for f in files[1:]:
        flag = False
        for o in output:
            if open(path+o[0], "r").read() == open(f, "r").read():
                o.append(f.split("\\")[-1])
                flag = True
                break
        if not flag:
            output.append([f.split("\\")[-1]])        
    ans = {}
    ans['matches'] = output
    return json.dumps(ans)
    

path = "" # please specify the given path here
compareFiles(path)


"""
Here, compareFiles function takes as input the path of the specified folder. 

The logic here is for each file, I compare it with contents of other files in the output array to see if the file has similar content to any other files. If yes, I append it to that particular list or else create a new list with current file. At the end, the function returns a json object as described in the problem.

Drawbacks : code written specific to Windows path format, path separator accepted is \\. Also, using read() function to do a string comparison of files could be inefficient if the files are too big.

Advantages : There's an on-fly comparison between the files, without using any buffer memory.
"""
