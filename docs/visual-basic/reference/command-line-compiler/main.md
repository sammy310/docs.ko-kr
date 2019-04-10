---
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: fd6240faf702ccb5e543bfd6a7779284f38d8850
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337242"
---
# <a name="-main"></a>-main
`Sub Main` 프로시저가 포함된 클래스 또는 모듈을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-main:location  
```  
  
## <a name="arguments"></a>인수  
 `location`  
 필수 요소. 클래스 또는 포함 된 모듈의 이름을 합니다 `Sub Main` 프로그램이 시작 될 때 호출 되는 프로시저입니다. 형태로 때문일 **-기본: module** 또는 **-main:namespace.module**합니다.  
  
## <a name="remarks"></a>설명  
 실행 파일 또는 프로그램을 실행 하는 Windows 만들 때이 옵션을 사용 합니다. 경우는 **-주** 옵션을 생략 하면, 컴파일러는 유효한 공유에 대 한 검색 `Sub Main` 모든 공용 클래스 및 모듈입니다.  
  
 참조 [Visual Basic의 Main 프로시저](../../../visual-basic/programming-guide/program-structure/main-procedure.md) 에 대 한 다양 한 형태의 설명은 `Main` 프로시저입니다.  
  
 때 `location` 는 클래스에서 상속 되는 <xref:System.Windows.Forms.Form>, 컴파일러는 기본 제공 `Main` 클래스에 없는 경우 응용 프로그램을 시작 하는 프로시저 `Main` 프로시저입니다. 이렇게 하면 개발 환경에서 생성 된 명령줄에서 코드를 컴파일할 수 있습니다.  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a>Visual Studio 통합된 개발 환경에서 기본 설정  
  
1. **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2. **응용 프로그램** 탭을 클릭합니다.  
  
3. 있는지 확인 합니다 **응용 프로그램 프레임 워크 사용** 확인란을 선택 하지 않습니다.  
  
4. 값을 수정 합니다 **시작 개체** 상자입니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `T2.vb` 및 `T3.vb`을 지정 하 고는 합니다 `Sub Main` 프로시저를 찾을 수는 `Test2` 클래스입니다.  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Visual Basic의 Main 프로시저](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
