# dsa11
# infytq question
#java code
#minimum distinct element after deleting k elements
import java.util.*;
public class Main
{
	public static void main(String[] args) 
	{
	    int count=3;
	    String	input="2 2 1 3 3";
	    String s[]=input.split(" ");
	    int num[]=new int[s.length];
	    HashMap<Integer, Integer> map = new HashMap<>();
	    for(int i=0;i<num.length;i++)
	    {
	        num[i]=Integer.parseInt(s[i]);
	        if(map.containsKey(num[i]))
	        map.put(num[i],map.get(num[i])+1);
	        else
	        map.put(num[i],1);
	    }
	    int freq[]=new int[map.size()];
	    int j=0;
	    for(Map.Entry<Integer,Integer>data:map.entrySet())
	    {
	         freq[j]=data.getValue();
	         j++;
	    }
	    Arrays.sort(freq);
	    for(int i=0;i<freq.length;i++)
	    {
	        if(freq[i]==1 && count!=0)
	        {
	            freq[i]=0;
	            count--;
	        }
	        else if(freq[i]>1)
	        {
	            while(freq[i]!=0 && count!=0)
	            {
	                freq[i]=freq[i]-1;
	                count--;
	            }
	        }
	        if(count==0)
	        break;
	    }
	    int ans=0;
	    for(int i=0;i<freq.length;i++)
	    {
	        if(freq[i]>0)
	        ans++;
	    }
	    System.out.println("    "+ans);
	}
}
