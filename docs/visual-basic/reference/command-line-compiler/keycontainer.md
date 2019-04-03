---
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
ms.openlocfilehash: 51cfe4a52af2fbcd51a4f9e2dc738e83fe0852c1
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839602"
---
# <a name="-keycontainer"></a>-keycontainer
어셈블리에 강력한 이름을 지정하는 키 쌍의 키 컨테이너 이름을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-keycontainer:container  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`container`|필수 요소. 키가 포함 된 컨테이너 파일입니다. 파일 이름을 따옴표로 묶습니다 ("") 이름에 공백이 있습니다.|  
  
## <a name="remarks"></a>설명  
 컴파일러는 공개 키를 어셈블리 매니페스트에 삽입 하 고 개인 키를 사용 하 여 최종 어셈블리에 서명 하 여 공유할 수 있는 구성 요소를 만듭니다. 키 파일을 생성하려면 명령줄에 `sn -k file`을 입력합니다. `-i` 옵션 컨테이너에 키 쌍을 설치 합니다. 자세한 내용은 [Sn.exe (강력한 이름 도구)](../../../framework/tools/sn-exe-strong-name-tool.md)).  
  
 사용 하 여 컴파일하면 `-target:module`를 키 파일의 이름이 모듈에 저장 되 고 사용 하 여 어셈블리를 컴파일할 때 생성 되는 어셈블리에 통합 [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)합니다.  
  
 MSIL(Microsoft Intermediate Language) 모듈의 소스 코드에서 이 옵션을 사용자 지정 특성(<xref:System.Reflection.AssemblyKeyNameAttribute>)으로 지정할 수도 있습니다.  
  
 [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)을 사용하여 암호화 정보를 컴파일러에 전달할 수도 있습니다. 부분 서명된 어셈블리가 필요한 경우 [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)을 사용합니다.  
  
 참조 [강력한 어셈블리 만들기 및 사용](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) 어셈블리 서명에 대 한 자세한 내용은 합니다.  
  
> [!NOTE]
>  `-keycontainer` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 있는 명령줄에서 컴파일할 경우에 사용할 수 있는 것입니다.  
  
## <a name="example"></a>예제  
 다음 코드는 소스 파일 `Input.vb` 키 컨테이너를 지정 합니다.  
  
```  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a>참고자료

- [.NET 어셈블리](../../../standard/assembly/index.md)
- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
