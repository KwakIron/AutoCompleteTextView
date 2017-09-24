# AutoCompleteTextView
```
public class MainActivity extends AppCompatActivity {
    //하나의 단어만 자동
    private AutoCompleteTextView atv_content;
    //여러개의 단어 자동
    private MultiAutoCompleteTextView matv_content;

    private static final String[] data = new String[]{
            "하늘나라", "개발자", "슈퍼맨", "부들부들", "ㅋㅋㅋㅋ"
    };

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        atv_content = (AutoCompleteTextView) findViewById(R.id.atv_content);
        matv_content = (MultiAutoCompleteTextView) findViewById(R.id.matv_content);

        ArrayAdapter<String> adapter = new ArrayAdapter<String>(this,android.R.layout.simple_dropdown_item_1line,data);
        atv_content.setAdapter(adapter);


        ArrayAdapter<String> adapter2 = new ArrayAdapter<String>(this,android.R.layout.simple_dropdown_item_1line,data);
        matv_content.setAdapter(adapter2);
        //단어하나마다 자동으로 점 찍기 
        matv_content.setTokenizer(new MultiAutoCompleteTextView.CommaTokenizer());
    }
}
