## 1. InputArray 클래스
* Mat, Mat<T>, Matx<T, m, n>, vector<T>, vector< vector<T> >, vector<Mat>, vector<Mat_<T> >, UMat, vector<UMat>, double 같은 다양한 타입으로부터 생성될 수 있는 인터페이스 클래스
* OpenCV 도움말 페이지에서 특정 함수의 인자가 InputArray 타입을 받도록 설명되어 있다면 Mat 클래스 객체 또는 vector<T> 타입의 변수를 전달하는 형태로 코드를 작성
* InputArray 타입의 함수 인자에 비어 있는 행렬을 전달하려면 함수 인자에 noArray() 또는 Mat()를 입력
```cpp
//  InputArray 클래스를 이용한 사용자 함수 정의
void InputArrayOp()
{
  uchar data1[] = { 1, 2, 3, 4, 5, 6 };
  // data1 배열 값을 원소로 갖는 2×3 행렬 mat1을 생성
  Mat mat1(2, 3, CV_8U, data1);
  // printMat() 함수에 Mat 클래스 객체를 전달하여 원소 값을 출력
  printMat(mat1); 
  
  // 세 개의 실수로 이루어진 vec1 벡터를 생성
  vector<float> vec1 = { 1.2f, 3.4f, -2.1f };
  // printMat() 함수에 vector<float> 객체를 전달하여 원소 값을 출력
  printMat(vec1);
}

void printMat(InputArray _mat)
{
  // InputArray 타입의 _mat 객체로부터 Mat 객체 mat를 생성
  Mat mat = _mat.getMat();
  cout << mat << endl;
}
```
## 2. OutputArray 클래스
* _OutputArray 클래스는 클래스 계층적으로 _InputArray 클래스를 상속받아 만들어졌으므로 OutputArray 클래스도 Mat 또는 vector<T> 같은 타입의 객체로부터 생성될 수 있는 인터페이스 클래스
* OpenCV 함수는 영상을 입력으로 받아 영상 처리를 수행하고, 그 결과를 다시 영상으로 생성하여 반환하는데 return 구문으로 반환하는 것이 아니라 보통 OutputArray 클래스의 참조를 함수 인자로 사용하여 결과 영상을 전달
* OutputArray 클래스도 InputArray와 마찬가지로 사용자가 직접 OutputArray 타입의 변수를 생성해서 사용하면 안 됨
