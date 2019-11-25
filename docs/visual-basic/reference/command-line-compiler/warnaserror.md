---
title: -warnaserror
ms.date: 03/13/2018
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
ms.openlocfilehash: f9ca5575e2a042d68fc490494f2e86991d58b80c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351703"
---
# <a name="-warnaserror-visual-basic"></a>-warnaserror(Visual Basic)
컴파일러가 첫 번째 발생하는 경고를 오류로 처리하도록 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|+ &#124; -|(선택 사항) 기본적으로 `-warnaserror-`가 적용됩니다. 경고가 발생해도 컴파일러가 출력 파일을 생성하지 못하도록 하지 않습니다. `-warnaserror+`와 동일한 `-warnaserror` 옵션은 경고가 오류로 처리되도록 합니다.|  
|`numberList`|(선택 사항) `-warnaserror` 옵션이 적용되는 경고 ID 번호의 쉼표로 구분된 목록입니다. 경고 ID를 지정하지 않으면 `-warnaserror` 옵션이 모든 경고에 적용됩니다.|  
  
## <a name="remarks"></a>주의  
 `-warnaserror` 옵션은 모든 경고를 오류로 처리합니다. 일반적으로 경고로 보고되는 모든 메시지가 대신 오류로 보고됩니다. 컴파일러는 이후 발생하는 같은 경고를 경고로 보고합니다.  
  
 기본적으로 `-warnaserror-`이 적용되며 경고가 정보 제공용으로만 사용되게 합니다. `-warnaserror+`와 동일한 `-warnaserror` 옵션은 경고가 오류로 처리되도록 합니다.  
  
 몇 개의 특정 경고만 오류로 처리하려는 경우 오류로 처리할 경고 번호의 쉼표로 구분된 목록을 지정할 수 있습니다.  
  
> [!NOTE]
> `-warnaserror` 옵션은 경고가 표시되는 방법을 제어하지 않습니다. 경고를 사용하지 않도록 설정하려면 [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) 옵션을 사용합니다.  
  
|Visual Studio IDE에서 모든 경고를 오류로 처리하도록 -warnaserror을 설정하려면|  
|---|  
|1.  Have a project selected in **Solution Explorer**. **프로젝트** 메뉴에서 **속성**을 클릭합니다. <br />2.  Click the **Compile** tab.<br />3.  Make sure the **Disable all warnings** check box is unchecked.<br />4.  Check the **Treat all warnings as errors** check box.|  
  
|Visual Studio IDE에서 특정 경고를 오류로 처리하도록 -warnaserror을 설정하려면|  
|---|  
|1.  Have a project selected in **Solution Explorer**. **프로젝트** 메뉴에서 **속성**을 클릭합니다.<br />2.  Click the **Compile** tab.<br />3.  Make sure the **Disable all warnings** check box is unchecked.<br />4.  Make sure the **Treat all warnings as errors** check box is unchecked.<br />5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.|  
  
## <a name="example"></a>예제  
 다음 코드에서는 `In.vb`를 컴파일하고 컴파일러가 찾는 모든 경고의 첫 번째 발생을 오류로 표시하도록 합니다.  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a>예제  
 다음 코드에서는 `T2.vb`를 컴파일하고 사용되지 않는 지역 변수(42024)에 대한 경고만 오류로 처리합니다.  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
