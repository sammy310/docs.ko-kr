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
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348563"
---
# <a name="-resource-visual-basic"></a>-resource (Visual Basic)
관리되는 리소스를 어셈블리에 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-resource:filename[,identifier[,public|private]]  
```

or  

```console
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`filename`|필수 요소. The name of the resource file to embed in the output file. By default, `filename` is public in the assembly. Enclose the file name in quotation marks (" ") if it contains a space.|  
|`identifier`|(선택 사항) The logical name for the resource; the name used to load it. 기본값은 파일 이름입니다. Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`|  
  
## <a name="remarks"></a>주의  
 Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.  
  
 If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information). To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.  
  
 `-resource`의 약식은 `-res`입니다.  
  
 For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
## <a name="example"></a>예제  
 The following code compiles `In.vb` and attaches resource file `Rf.resource`.  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
