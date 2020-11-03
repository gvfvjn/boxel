# boxel
this is my c based so most of the things I don't talk about are the same as c.
this is a hello world in boxel
```
use main;

act 1 {
    phase main {
        func void Main {
            $ this is a comment $
            Sys.LineOut("hello world");
        }
    }
    start(main)
} 
```
boxel is based on acts and phases.phase can edit other phases.
```
use main;

act editable_test {
    phase main {
        func void Main {
            $ an editable is declared by(editable,name)(default) $
            if((editable,if)(int 10)>9) {
                Sys.LineOut("t");
            }
        }
    }
    phase test {
        func void main() {
            int inp=To.Int(Sys.LineIn());
            $to edit a editable you type act.phase(name,value)$
            editable_test.main(if,inp);
            $ start is how you switch from phase to phase
            start(main);
        }
    }
    start(test);
}
```
acts are basically phases that contain phases.boxel also has classes but I wont talk about them now.
editables can be more than just integers thay can be whole lines of code like this
```
use main;

act editables {
    phase main {
        func void main() {
            bool i=true;
            (editable stat)(code if(i)) {
                Sys.LineOut("oki")
            }
        }
    }
    phase test {
        func void main() {
            Sys.LineOut("if or while");
            string y_or_n=Sys.LineIn();
            if(y_or_no=="if") {
                editables.main(stat,while(i));
            }
            start(main);
        }
    }
    start(test);
}
```
