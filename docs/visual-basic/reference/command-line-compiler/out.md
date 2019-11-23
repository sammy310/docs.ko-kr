---
title: -out
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 67366e13e4dceea4772d0730222413cb25b4e8b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352383"
---
# <a name="-out-visual-basic"></a>-out (Visual Basic)
출력 파일의 이름을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`filename`|필수 요소. The name of the output file the compiler creates. If the file name contains a space, enclose the name in quotation marks (" ").|  
  
## <a name="remarks"></a>주의  
 Specify the full name and extension of the file to create. If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.  
  
 If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.  
  
|To set -out in the Visual Studio integrated development environment|  
|---|  
|1.  Have a project selected in **Solution Explorer**. **프로젝트** 메뉴에서 **속성**을 클릭합니다. <br />2.  **애플리케이션** 탭을 클릭합니다.<br />3.  Modify the value in the **Assembly Name** box.|  
  
## <a name="example"></a>예제  
 The following code compiles `T2.vb` and creates output file `T2.exe`.  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
