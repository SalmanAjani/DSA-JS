Solution :-

    var romanToInt = function(s) {
        let symbols = {
            I : 1,
            V : 5,
            X : 10,
            L : 50,
            C : 100,
            D : 500,
            M : 1000
        }
        let res = 0;

        for(let i=0; i<s.length; i++){
            const curr = symbols[s[i]];
            const next = symbols[s[i+1]];

            if(curr < next){
                res += next-curr;
                i++;
            }
            else{
                res += curr;
            }
        }

        return res;
    };
