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
ms.translationtype: MT
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
 필수 사항입니다. 키가 포함된 파일입니다. 파일 이름에 공백이 포함된 경우 이름을 따옴표("")로 둘러싸습니다.  
  
## <a name="remarks"></a>설명  
 컴파일러는 공개 키를 어셈블리 매니페스트에 삽입한 다음 개인 키로 최종 어셈블리에 서명합니다. 키 파일을 생성하려면 명령줄에 `sn -k file`을 입력합니다. 자세한 내용은 [Sn.exe(강력한 이름 도구)를](../../../framework/tools/sn-exe-strong-name-tool.md)참조하십시오.  
  
 을 사용 `-target:module`하 고 컴파일하는 경우 키 파일의 이름은 모듈에 보관되고 [-addmodule을](../../../visual-basic/reference/command-line-compiler/addmodule.md)사용 하 고 어셈블리를 컴파일할 때 생성 되는 어셈블리에 통합 됩니다.  
  
 [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)를 사용하여 암호화 정보를 컴파일러에 전달할 수도 있습니다. 부분 서명된 어셈블리가 필요한 경우 [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)을 사용합니다.  
  
 Microsoft 중간 언어 모듈의 소스<xref:System.Reflection.AssemblyKeyFileAttribute>코드에서 이 옵션을 사용자 지정 특성()으로 지정할 수도 있습니다.  
  
 동일한 컴파일에서 명령줄 옵션 또는 사용자 지정 특성에 의해 모두 `-keyfile` 및 [-keycontainer가](../../../visual-basic/reference/command-line-compiler/keycontainer.md) 지정되는 경우 컴파일러는 먼저 키 컨테이너를 시도합니다. 키 컨테이너를 찾으면 키 컨테이너의 정보를 사용하여 어셈블리가 서명됩니다. 컴파일러에서 키 컨테이너를 찾지 못하면 `-keyfile`로 지정된 파일을 시도합니다. 이 문제가 성공하면 어셈블리는 키 파일의 정보로 서명되고 키 정보가 키 컨테이너에 `sn -i`설치되므로 다음 컴파일에서 키 컨테이너가 유효합니다.  
  
 키 파일에는 공개 키만 포함될 수 있습니다.  
  
 어셈블리 서명에 대한 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용을](../../../standard/assembly/create-use-strong-named.md) 참조하십시오.  
  
> [!NOTE]
> 이 `-keyfile` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다. 명령줄에서 컴파일할 때만 사용할 수 있습니다.

## <a name="example"></a>예제

다음 코드는 소스 `Input.vb` 파일을 컴파일하고 키 파일을 지정합니다.

```console
vbc -keyfile:myfile.sn input.vb
```

## <a name="see-also"></a>참고 항목

- [.NET 어셈블리](../../../standard/assembly/index.md)
- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [- 참조 (비주얼 베이직)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
