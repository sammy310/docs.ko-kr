---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: cffc3c5f0ff3dd48ca2c74bde346a967b209dc5f
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266744"
---
# <a name="-keyfile"></a>-keyfile
어셈블리에 강력한 이름을 지정하는 키 또는 키 쌍이 포함된 파일을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```console
-keyfile:file  
```  
  
## <a name="arguments"></a>인수  
 `file`  
 필수 요소. 키를 포함하는 파일입니다. 파일 이름에 공백이 있으면 이름을 따옴표(" ")로 묶습니다.  
  
## <a name="remarks"></a>설명  
 컴파일러는 공개 키를 어셈블리 매니페스트에 삽입한 다음, 프라이빗 키를 사용하여 최종 어셈블리에 서명합니다. 키 파일을 생성하려면 명령줄에 `sn -k file`을 입력합니다. 자세한 내용은 [Sn.exe(강력한 이름 도구)](../../../framework/tools/sn-exe-strong-name-tool.md)를 참조하세요.  
  
 `-target:module`로 컴파일하는 경우 키 파일의 이름이 모듈에 저장되고, [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)을 사용하여 어셈블리를 컴파일할 때 생성되는 어셈블리에 통합됩니다.  
  
 [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)를 사용하여 암호화 정보를 컴파일러에 전달할 수도 있습니다. 부분 서명된 어셈블리가 필요한 경우 [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)을 사용합니다.  
  
 Microsoft 중간 언어 모듈의 소스 코드에서 이 옵션을 사용자 지정 특성(<xref:System.Reflection.AssemblyKeyFileAttribute>)으로 지정할 수도 있습니다.  
  
 동일한 컴파일에서 `-keyfile` 및 [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)를 명령줄 옵션이나 사용자 지정 특성으로 둘 다 지정하면 컴파일러는 먼저 키 컨테이너를 찾으려고 합니다. 키 컨테이너를 찾으면 키 컨테이너의 정보를 사용하여 어셈블리가 서명됩니다. 컴파일러는 키 컨테이너를 찾지 못할 경우 `-keyfile`로 지정된 파일을 찾으려고 합니다. 해당 파일을 찾으면 키 파일의 정보를 사용하여 어셈블리가 서명되고, 키 정보가 키 컨테이너에 설치되므로(`sn -i`와 유사) 다음에 컴파일할 때 키 컨테이너가 유효해집니다.  
  
 키 파일에는 공개 키만 포함될 수 있습니다.  
  
 어셈블리 서명에 대한 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../../../standard/assembly/create-use-strong-named.md)을 참조하세요.  
  
> [!NOTE]
> Visual Studio 개발 환경 내에서는 `-keyfile` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.

## <a name="example"></a>예제

다음 코드는 `Input.vb` 소스 파일을 컴파일하고 키 파일을 지정합니다.

```console
vbc -keyfile:myfile.sn input.vb
```

## <a name="see-also"></a>참조

- [.NET 어셈블리](../../../standard/assembly/index.md)
- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-reference(Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
