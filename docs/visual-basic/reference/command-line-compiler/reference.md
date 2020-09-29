---
title: -reference
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
ms.openlocfilehash: b489a164e56a5e3bdbf7e3cdf24ec330fadedf38
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097555"
---
# <a name="-reference-visual-basic"></a>-reference(Visual Basic)

컴파일러에서 지정된 어셈블리의 형식 정보를 현재 컴파일하고 있는 프로젝트에 사용할 수 있도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-reference:fileList  
```

또는

```console
-r:fileList  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`fileList`|필수 요소. 쉼표로 구분된 어셈블리 파일 이름 목록입니다. 파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다.|  
  
## <a name="remarks"></a>설명  

 가져오는 파일에는 어셈블리 메타데이터가 포함되어야 합니다. 어셈블리 외부에는 public 형식만 표시됩니다. [-addmodule](addmodule.md) 옵션은 모듈에서 메타데이터를 가져옵니다.  
  
 다른 어셈블리(어셈블리 B) 자체를 참조하는 어셈블리(어셈블리 A)를 참조하면 다음과 같은 경우 어셈블리 B를 참조해야 합니다.  
  
- 어셈블리 A의 형식은 형식에서 상속되거나 어셈블리 B의 인터페이스를 구현합니다.  
  
- 어셈블리 B의 반환 형식이나 매개 변수 형식을 사용하는 필드, 속성, 이벤트 또는 메서드가 호출됩니다.  
  
 [-libpath](libpath.md)를 사용하여 하나 이상의 어셈블리 참조가 있는 디렉터리를 지정합니다.  
  
 컴파일러가 모듈이 아닌 어셈블리의 형식을 인식하도록 하려면 강제로 형식을 확인해야 합니다. 이 작업을 수행하는 방법의 한 예는 형식의 인스턴스를 정의하는 것입니다. 컴파일러에 대한 어셈블리의 형식 이름을 확인하는 데 사용할 수 있는 다른 방법이 있습니다. 예를 들어, 어셈블리의 형식에서 상속되는 경우 형식 이름이 컴파일러에 알려지게 됩니다.  
  
 일반적으로 사용되는 .NET Framework 어셈블리를 참조하는 Vbc.rsp 지시 파일이 기본적으로 사용됩니다. 컴파일러에서 Vbc.rsp를 사용하지 않도록 하려면 `-noconfig`를 사용합니다.  
  
 `-reference`의 약식은 `-r`입니다.  
  
## <a name="example"></a>예제  

 다음 명령은 원본 파일 `Input.vb`와 `Metad1.dll` 및 `Metad2.dll`의 참조 어셈블리를 컴파일하여 `Out.exe`를 생성합니다.  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [-noconfig](noconfig.md)
- [-target(Visual Basic)](target.md)
- [공용](../../language-reference/modifiers/public.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
