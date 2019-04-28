---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: c13f34c23cad9c909c2c5bd3447f1a8fa53f9b4d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793965"
---
# <a name="-keyfile"></a>-keyfile
어셈블리에 강력한 이름을 지정하는 키 또는 키 쌍이 포함된 파일을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
``` 
-keyfile:file  
```  
  
## <a name="arguments"></a>인수  
 `file`  
 필수 요소. 키가 포함 된 파일입니다. 파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다 ("").  
  
## <a name="remarks"></a>설명  
 컴파일러는 공개 키를 어셈블리 매니페스트에 삽입 하 고 개인 키를 사용 하 여 최종 어셈블리에 서명 합니다. 키 파일을 생성하려면 명령줄에 `sn -k file`을 입력합니다. 자세한 내용은 [Sn.exe (강력한 이름 도구)](../../../framework/tools/sn-exe-strong-name-tool.md)).  
  
 사용 하 여 컴파일하면 `-target:module`를 키 파일의 이름이 모듈에 저장 되 고 사용 하 여 어셈블리를 컴파일할 때 생성 되는 어셈블리에 통합 [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)합니다.  
  
 [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)를 사용하여 암호화 정보를 컴파일러에 전달할 수도 있습니다. 부분 서명된 어셈블리가 필요한 경우 [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)을 사용합니다.  
  
 사용자 지정 특성으로이 옵션을 지정할 수도 있습니다 (<xref:System.Reflection.AssemblyKeyFileAttribute>) 모든 Microsoft intermediate language 모듈에 대 한 소스 코드에 있습니다.  
  
 경우 둘 다 `-keyfile` 하 고 [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) 에 지정 된 (명령줄 옵션이 나 사용자 지정 특성) 같은 컴파일, 컴파일러는 먼저 키 컨테이너를 찾으려고 합니다. 키 컨테이너를 찾으면 키 컨테이너의 정보를 사용하여 어셈블리가 서명됩니다. 컴파일러는 키 컨테이너를 찾지 못하면 지정 된 파일은 시도 `-keyfile`합니다. 이 작업이 성공 하면, 키 파일에서 정보를 사용 하 여 어셈블리가 서명 되 고 키 정보가 키 컨테이너에 설치 됩니다 (비슷합니다 `sn -i`) 다음에 컴파일할 키 컨테이너를 사용할 수 있도록 합니다.  
  
 키 파일에는 공개 키만 포함될 수 있습니다.  
  
 참조 [강력한 어셈블리 만들기 및 사용](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) 어셈블리 서명에 대 한 자세한 내용은 합니다.  
  
> [!NOTE]
>  `-keyfile` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 있는 명령줄에서 컴파일할 경우에 사용할 수 있는 것입니다.  
  
## <a name="example"></a>예제  
 다음 코드는 소스 파일 `Input.vb` 키 파일을 지정 합니다.  
  
```console  
vbc -keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a>참고자료

- [.NET 어셈블리](../../../standard/assembly/index.md)
- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-참조 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
