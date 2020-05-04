---
title: -resource
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: a781d543dd32ffb3d0ac0b11c544dbfd8cd5d806
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348563"
---
# <a name="-resource-visual-basic"></a>-resource(Visual Basic)
관리되는 리소스를 어셈블리에 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-resource:filename[,identifier[,public|private]]  
```

또는  

```console
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`filename`|필수 요소. 출력 파일에 포함할 리소스 파일의 이름입니다. 기본적으로 `filename`은 어셈블리에서 공용입니다. 공백이 있으면 파일 이름을 따옴표(" ")로 묶습니다.|  
|`identifier`|선택 사항입니다. 리소스의 논리적 이름, 즉 리소스를 로드하는 데 사용되는 이름입니다. 기본값은 파일 이름입니다. 필요에 따라 다음과 같이 리소스를 어셈블리 매니페스트에서 공용 또는 전용으로 지정할 수 있습니다. `-res:filename.res, myname.res, public`|  
  
## <a name="remarks"></a>설명  
 리소스 파일을 출력 파일에 배치하지 않고 어셈블리에 리소스를 연결하려면 `-linkresource`를 사용합니다.  
  
 예를 들어, `filename`이 [Resgen.exe(리소스 파일 생성기)](../../../framework/tools/resgen-exe-resource-file-generator.md)에 의해 또는 개발 환경에서 만들어진 .NET Framework 리소스 파일인 경우에는 <xref:System.Resources> 네임스페이스의 멤버를 사용하여 해당 파일에 액세스할 수 있습니다(자세한 내용은 <xref:System.Resources.ResourceManager> 참조). 런타임에 다른 모든 리소스에 액세스하려면 다음 메서드 중 하나를 사용합니다. <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A> 또는 <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.  
  
 `-resource`의 약식은 `-res`입니다.  
  
 Visual Studio IDE에서 `-resource`를 설정하는 방법에 대한 자세한 내용은 [애플리케이션 리소스 관리(.NET)](/visualstudio/ide/managing-application-resources-dotnet)를 참조하세요.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `In.vb`를 컴파일하고 리소스 파일 `Rf.resource`를 연결합니다.  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [-linkresource(Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [-target(Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
