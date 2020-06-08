---
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: 5530da4c784346df4a1088998b8d2027feee08e3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403163"
---
# <a name="-main"></a>-main
`Sub Main` 프로시저가 포함된 클래스 또는 모듈을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-main:location  
```  
  
## <a name="arguments"></a>인수  
 `location`  
 필수 요소. 프로그램이 시작할 때 호출될 `Sub Main` 프로시저를 포함하는 클래스 또는 모듈의 이름입니다. **-main:module** 또는 **-main:namespace.module** 형태일 수 있습니다.  
  
## <a name="remarks"></a>설명  
 실행 파일 또는 Windows 실행 프로그램을 만들 때 이 옵션을 사용합니다. **-main** 옵션을 생략하면 컴파일러가 모든 공용 클래스 및 모듈에서 유효한 공유 `Sub Main`을 검색합니다.  
  
 `Main` 프로시저의 다양한 형태에 대한 설명은 [Visual Basic의 Main 프로시저](../../programming-guide/program-structure/main-procedure.md)를 참조하세요.  
  
 `location`이 <xref:System.Windows.Forms.Form>으로부터 상속하는 클래스인 경우 컴파일러는 클래스에 `Main` 프로시저가 없는 경우 애플리케이션을 시작하는 기본 `Main` 프로시저를 제공합니다. 이를 통해 개발 환경에서 만든 코드를 명령줄에서 컴파일할 수 있습니다.  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a>Visual Studio 통합 개발 환경에서 -main을 설정하려면  
  
1. **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2. **애플리케이션** 탭을 클릭합니다.  
  
3. **애플리케이션 프레임워크 사용** 확인란이 선택되지 않았는지 확인합니다.  
  
4. **시작 개체** 상자에서 값을 수정합니다.  
  
## <a name="example"></a>예제  
 다음 코드는 `Test2` 클래스에서 `Sub Main` 프로시저를 찾을 수 있도록 지정하여 `T2.vb` 및 `T3.vb`를 컴파일합니다.  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [-target(Visual Basic)](target.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
- [Visual Basic의 Main 프로시저](../../programming-guide/program-structure/main-procedure.md)
