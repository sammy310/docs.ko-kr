---
title: -linkresource
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: 43ebb61efa26ed11af573e2c4e73a6fd71ac0902
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403202"
---
# <a name="-linkresource-visual-basic"></a>-linkresource(Visual Basic)
관리되는 리소스에 대한 링크를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-linkresource:filename[,identifier[,public|private]]  
```

또는  

```console
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>인수  
 `filename`  
 필수 요소. 어셈블리에 연결할 리소스 파일입니다. 파일 이름에 공백이 있으면 이름을 따옴표(" ")로 묶습니다.  
  
 `identifier`  
 선택 사항입니다. 리소스의 논리적 이름입니다. 리소스를 로드하는 데 사용되는 이름입니다. 기본값은 파일 이름입니다. 필요에 따라 셈블리 매니페스트에서 파일을 퍼블릭 또는 프라이빗으로 지정할 수 있습니다(예: `-linkres:filename.res,myname.res,public`). 기본적으로 `filename`은 어셈블리에서 퍼블릭입니다.  
  
## <a name="remarks"></a>설명  
 `-linkresource` 옵션은 출력 파일에 리소스 파일을 포함하지 않습니다. 이 작업을 수행하려면 `-resource` 옵션을 사용합니다.  
  
 `-linkresource` 옵션에는 `-target:module` 이외의 `-target` 옵션 중 하나가 필요합니다.  
  
 예를 들어, `filename`이 [Resgen.exe(리소스 파일 생성기)](../../../framework/tools/resgen-exe-resource-file-generator.md) 또는 개발 환경에서 만들어진 .NET Framework 리소스 파일인 경우 <xref:System.Resources> 네임스페이스의 멤버를 사용하여 액세스할 수 있습니다. (자세한 내용은 <xref:System.Resources.ResourceManager>를 참조하세요.) 런타임 시 다른 모든 리소스에 액세스하려면 <xref:System.Reflection.Assembly> 클래스에서 `GetManifestResource`로 시작하는 메서드를 사용합니다.  
  
 파일 이름은 모든 파일 형식이 될 수 있습니다. 예를 들어 네이티브 DLL을 어셈블리의 일부로 설정하면 전역 어셈블리 캐시에 설치하고 어셈블리의 관리 코드에서 액세스할 수 있습니다.  
  
 `-linkresource`의 약식은 `-linkres`입니다.  
  
> [!NOTE]
> Visual Studio 개발 환경에서는 `-linkresource` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `in.vb`를 컴파일하고 리소스 파일 `rf.resource`에 연결합니다.  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [-target(Visual Basic)](target.md)
- [-resource(Visual Basic)](resource.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
