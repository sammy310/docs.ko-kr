---
description: '자세한 정보: -nowarn'
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 4fb7d39aef48ff1443c342367f9e20bb37f9c5e0
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434864"
---
# <a name="-nowarn"></a>-nowarn

컴파일러에서 경고를 생성하지 않도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`numberList`|선택 사항입니다. 컴파일러가 표시하지 않아야 하는 경고 ID 번호의 쉼표로 구분된 목록입니다. 경고 ID를 지정하지 않으면 모든 경고가 표시되지 않습니다.|  
  
## <a name="remarks"></a>설명  

 `-nowarn` 옵션은 컴파일러에서 경고를 생성하지 않도록 합니다. 개별 경고를 표시하지 않으려면 콜론 뒤에 있는 `-nowarn` 옵션에 경고 ID를 제공합니다. 여러 경고 번호를 쉼표로 구분합니다.  
  
 경고 식별자의 숫자 부분만 지정하면 됩니다. 예를 들어 사용하지 않은 지역 변수에 대한 경고인 BC42024를 표시하지 않으려면 `-nowarn:42024`를 지정합니다.  
  
 경고 ID 번호에 대한 자세한 내용은 [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
|Visual Studio 통합 개발 환경에서 -nowarn을 설정하려면 다음을 수행합니다.|  
|---|  
|1.  **솔루션 탐색기** 에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성** 을 클릭합니다. <br />2.  **컴파일** 탭을 클릭합니다.<br />3.  **모든 경고 사용 안 함** 확인란을 선택하여 모든 경고를 사용하지 않습니다.<br />     또는<br />     특정 경고를 사용하지 않도록 설정하려면 경고 옆의 드롭다운 목록에서 **없음** 을 클릭합니다.|  
  
## <a name="example"></a>예제  

 다음 코드에서는 `T2.vb`를 컴파일하고 경고를 표시하지 않습니다.  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a>예제  

 다음 코드에서는 `T2.vb`를 컴파일하고 사용되지 않는 지역 변수(42024)에 대한 경고를 표시하지 않습니다.  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
- [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
