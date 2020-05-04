---
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
ms.openlocfilehash: be2ad1416e801398fb513593c7f3828e5488bfaf
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005535"
---
# <a name="-keycontainer"></a>-keycontainer
어셈블리에 강력한 이름을 지정하는 키 쌍의 키 컨테이너 이름을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-keycontainer:container  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`container`|필수 요소. 키를 포함하는 컨테이너 파일입니다. 파일 이름에 공백이 있으면 이름을 따옴표("")로 묶습니다.|  
  
## <a name="remarks"></a>설명  
 컴파일러는 공개 키를 어셈블리 매니페스트에 삽입하고 최종 어셈블리를 프라이빗 키로 서명하여 공유 가능한 구성 요소를 만듭니다. 키 파일을 생성하려면 명령줄에 `sn -k file`을 입력합니다. `-i` 옵션은 컨테이너에 키 쌍을 설치합니다. 자세한 내용은 [Sn.exe(강력한 이름 도구)](../../../framework/tools/sn-exe-strong-name-tool.md)를 참조하세요.  
  
 `-target:module`로 컴파일하는 경우 키 파일의 이름이 모듈에 저장되고, [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)을 사용하여 어셈블리를 컴파일할 때 생성되는 어셈블리에 통합됩니다.  
  
 MSIL(Microsoft Intermediate Language) 모듈의 소스 코드에서 이 옵션을 사용자 지정 특성(<xref:System.Reflection.AssemblyKeyNameAttribute>)으로 지정할 수도 있습니다.  
  
 [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)을 사용하여 암호화 정보를 컴파일러에 전달할 수도 있습니다. 부분 서명된 어셈블리가 필요한 경우 [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)을 사용합니다.  
  
 어셈블리 서명에 대한 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../../../standard/assembly/create-use-strong-named.md)을 참조하세요.  
  
> [!NOTE]
> Visual Studio 개발 환경 내에서는 `-keycontainer` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드는 소스 파일 `Input.vb`를 컴파일하고 키 컨테이너를 지정합니다.  
  
```console  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a>참조

- [.NET 어셈블리](../../../standard/assembly/index.md)
- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
