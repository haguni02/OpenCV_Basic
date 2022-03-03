## FileStorage 클래스
* OpenCV에서 Mat 클래스에 저장된 영상 데이터는 imwrite() 함수를 이용하여 BMP, JPG, PNG 등 영상 파일로 저장할 수 있으나 uchar 자료형을 사용하는 영상 데이터가 아니라 int, float, double 등의 자료형을 사용하는 일반적인 행렬은 영상 파일 형식으로 저장할 수 없음
* OpenCV에서 제공하는 FileStorage 클래스는 Mat 클래스 객체뿐만 아니라 일반적인 C/C++ 자료형 데이터를 XML, YAML, JSON 등 파일 형식으로 저장하는 기능을 제공
```cpp
// 간략화한 FileStorage 클래스 정의
class FileStorage
02    {
03    public:
04        FileStorage();
05        FileStorage(const String& filename, int flags, const String& encoding=String());
06

07        virtual bool open(const String& filename, int flags,
08                          const String& encoding=String());
09        virtual bool isOpened() const;
10        virtual void release();
11

12        FileNode operator[](const char* nodename) const;
13        …
14    };
15

16    template<typename _Tp> static
17    FileStorage& operator << (FileStorage& fs, const _Tp& value);
18    static FileStorage& operator << (FileStorage& fs, const String& str);
19    static FileStorage& operator << (FileStorage& fs, const char* str);
20

21    template<typename _Tp> static
22    void operator >> (const FileNode& n, _Tp& value)
23    template<typename _Tp> static
24    void operator >> (const FileNode& n, std::vector<_Tp>& vec)
```
