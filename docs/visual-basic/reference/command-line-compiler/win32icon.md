---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: dc48a8f79aa04892c514917da00b8fd6489695b1
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593090"
---
# <a name="-win32icon"></a>-win32icon
출력 파일에.ico 파일을 삽입합니다. 이.ico 파일에 출력 파일을 나타내는 **파일 탐색기**합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-win32icon:filename  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`filename`|출력 파일에 추가할.ico 파일입니다. 파일 이름을 따옴표로 묶습니다 ("")에 공백이 있는 경우.|  
  
## <a name="remarks"></a>설명  
 Microsoft Windows 리소스 컴파일러 (RC) 사용 하 여.ico 파일을 만들 수 있습니다. 리소스 컴파일러를 호출 하는 시각적 개체를 컴파일할 때 C++ 프로그램; .ico 파일은.rc 파일에서 생성 됩니다. 합니다 `-win32icon` 고 `-win32resource` 옵션은 상호 배타적입니다.  
  
 참조 [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) .NET Framework 리소스 파일을 참조 하 또는 [-리소스 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) .NET Framework 리소스 파일을 연결 합니다. 참조 [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) .res 파일을 가져옵니다.  
  
|설정-Visual Studio IDE에서 win32icon|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다. <br />2.  **응용 프로그램** 탭을 클릭합니다.<br />3.  값을 수정 합니다 **아이콘** 상자입니다.|  
  
## <a name="example"></a>예제  
 다음 코드 컴파일을 `In.vb` .ico 파일을 연결 하 고 `Rf.ico`입니다.  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
