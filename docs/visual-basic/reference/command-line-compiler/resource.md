---
title: -리소스 (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: 2d7da572ecc8d7d20917eaa244eefbcd7abe61f0
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589515"
---
# <a name="-resource-visual-basic"></a>-리소스 (Visual Basic)
관리되는 리소스를 어셈블리에 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-resource:filename[,identifier[,public|private]]  
' -or-  
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`filename`|필수 요소. 출력 파일에 포함할 리소스 파일의 이름입니다. 기본적으로 `filename` 어셈블리에 공개 합니다. 파일 이름을 따옴표로 묶습니다 ("")에 공백이 있는 경우.|  
|`identifier`|선택 사항입니다. 리소스에 대 한 논리적 이름 로드 하는 데 사용 하는 이름입니다. 기본값은 파일 이름입니다. 필요에 따라 다음와 마찬가지로 리소스는 공용 또는 개인 어셈블리 매니페스트에 여부를 지정할 수 있습니다. `-res:filename.res, myname.res, public`|  
  
## <a name="remarks"></a>설명  
 사용 하 여 `-linkresource` 출력 파일에 리소스 파일을 배치 하지 않고 어셈블리에 리소스를 연결 합니다.  
  
 경우 `filename` .NET Framework 리소스 파일이 만들어지면 예를 들어 여는 [Resgen.exe (리소스 파일 생성기)](../../../framework/tools/resgen-exe-resource-file-generator.md) 개발 환경에서의 멤버를 사용 하 여 액세스할 수 있습니다 또는 <xref:System.Resources> 네임 스페이스 (참조 <xref:System.Resources.ResourceManager> 자세한 정보에 대 한). 런타임 시 다른 모든 리소스에 액세스 하려면 다음 방법 중 하나를 사용 합니다. <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, 또는 <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>합니다.  
  
 `-resource`의 약식은 `-res`입니다.  
  
 설정 하는 방법에 대 한 자세한 `-resource` Visual Studio IDE에서 참조 [응용 프로그램 리소스 관리 (.NET)](/visualstudio/ide/managing-application-resources-dotnet)합니다.  
  
## <a name="example"></a>예제  
 다음 코드 컴파일을 `In.vb` 와 연결 합니다. 리소스 파일 `Rf.resource`합니다.  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
