---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 31f7a2b771cfa1bcc6581d720aa0de3505aec826
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788988"
---
# <a name="-nowarn"></a>-nowarn
컴파일러에서 경고를 생성하지 않도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`numberList`|선택 사항입니다. 컴파일러 억제 해야 하는 경고 ID 번호의 쉼표로 구분 된 목록입니다. 경고 Id를 지정 하지 않은 경우 모든 경고가 표시 되지 않습니다.|  
  
## <a name="remarks"></a>설명  
 `-nowarn` 옵션을 사용 하면 경고가 생성 되지 않습니다. 개별 경고를 표시 하지 않으려면 경고의 ID를 제공 합니다 `-nowarn` 콜론 뒤 옵션입니다. 여러 경고 번호를 쉼표로 구분 합니다.  
  
 경고 식별자의 숫자 부분만 지정 해야 합니다. BC42024, 사용 되지 않는 로컬 변수에 대 한 경고를 표시 하지 않으려는 경우 지정 하는 예를 들어 `-nowarn:42024`합니다.  
  
 경고 ID 번호에 대 한 자세한 내용은 참조 하세요. [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.  
  
|Visual Studio 통합된 개발 환경에서-nowarn를 설정 하려면|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다. <br />2.  **컴파일** 탭을 클릭합니다.<br />3.  선택 된 **모든 경고 사용 안 함** 모든 경고를 사용 하지 않도록 설정 하려면 확인란 합니다.<br />     또는<br />     특정 경고를 해제 하려면 **None** 경고 옆의 드롭다운 목록에서.|  
  
## <a name="example"></a>예제  
 다음 코드에서는 `T2.vb` 모든 경고를 표시 하지 않습니다.  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a>예제  
 다음 코드에서는 `T2.vb` 를 사용 하지 않는 로컬 변수 (42024)에 대 한 경고를 표시 하지 않습니다.  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
