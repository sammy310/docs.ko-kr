---
title: -vbruntime
ms.date: 03/13/2018
f1_keywords:
- vbruntime
- -vbruntime
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
ms.openlocfilehash: 46d4b095d4a2bf9aac9124d5d4b2a09adb347ba1
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085063"
---
# <a name="-vbruntime"></a>-vbruntime

컴파일러에서 Visual Basic 런타임 라이브러리에 대한 참조 없이 컴파일하거나 특정 런타임 라이브러리를 참조하여 컴파일하도록 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a>인수  

 \-  
 Visual Basic 런타임 라이브러리에 대한 참조 없이 컴파일합니다.  
  
 \+  
 기본 Visual Basic 런타임 라이브러리에 대한 참조로 컴파일합니다.  
  
 \*  
 Visual Basic 런타임 라이브러리에 대한 참조 없이 컴파일하고 Visual Basic 런타임 라이브러리의 핵심 기능을 어셈블리에 포함합니다.  
  
 `path`  
 지정된 라이브러리(DLL)에 대한 참조로 컴파일합니다.  
  
## <a name="remarks"></a>설명  

 `-vbruntime` 컴파일러 옵션을 사용하면 컴파일러가 Visual Basic 런타임 라이브러리에 대한 참조 없이 컴파일하도록 지정할 수 있습니다. Visual Basic 런타임 라이브러리에 대한 참조 없이 컴파일하는 경우 Visual Basic 런타임 도우미에 대한 호출을 생성하는 코드 또는 언어 구문에 오류 또는 경고가 기록됩니다. (*Visual Basic 런타임 도우미*는 특정 언어 의미 체계를 실행하기 위해 런타임에 호출되는 Microsoft.VisualBasic.dll에 정의된 함수입니다.)  
  
 `-vbruntime+` 옵션은 `-vbruntime` 스위치가 지정되지 않은 경우에 발생하는 것과 동일한 동작을 생성합니다. `-vbruntime+` 옵션을 사용하여 이전 `-vbruntime` 스위치를 재정의할 수 있습니다.  
  
 `-vbruntime-` 또는 `-vbruntime:path` 옵션을 사용하면 `My` 형식의 대부분의 개체를 사용할 수 없습니다.  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a>Visual Basic 런타임 핵심 기능 포함  

 `-vbruntime*` 옵션을 사용하면 런타임 라이브러리에 대한 참조 없이 컴파일할 수 있습니다. 대신 Visual Basic 런타임 라이브러리의 핵심 기능이 사용자 어셈블리에 포함되어 있습니다. Visual Basic 런타임을 포함하지 않는 플랫폼에서 애플리케이션을 실행하는 경우 이 옵션을 사용할 수 있습니다.  
  
 다음 런타임 멤버가 포함되어 있습니다.  
  
- <xref:Microsoft.VisualBasic.CompilerServices.Conversions> 클래스  
  
- <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> 메서드  
  
- <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> 메서드  
  
- <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> 메서드  
  
- <xref:Microsoft.VisualBasic.Constants.vbBack> 상수  
  
- <xref:Microsoft.VisualBasic.Constants.vbCr> 상수  
  
- <xref:Microsoft.VisualBasic.Constants.vbCrLf> 상수  
  
- <xref:Microsoft.VisualBasic.Constants.vbFormFeed> 상수  
  
- <xref:Microsoft.VisualBasic.Constants.vbLf> 상수  
  
- <xref:Microsoft.VisualBasic.Constants.vbNewLine> 상수  
  
- <xref:Microsoft.VisualBasic.Constants.vbNullChar> 상수  
  
- <xref:Microsoft.VisualBasic.Constants.vbNullString> 상수  
  
- <xref:Microsoft.VisualBasic.Constants.vbTab> 상수  
  
- <xref:Microsoft.VisualBasic.Constants.vbVerticalTab> 상수  
  
- `My` 형식의 일부 개체  
  
 `-vbruntime*` 옵션을 사용하여 컴파일하고 코드가 핵심 기능에 포함되지 않은 Visual Basic 런타임 라이브러리의 멤버를 참조하는 경우 컴파일러에서 해당 멤버를 사용할 수 없음을 나타내는 오류를 반환합니다.  
  
## <a name="referencing-a-specified-library"></a>지정된 라이브러리 참조  

 `path` 인수를 사용하여 기본 Visual Basic 런타임 라이브러리 대신 사용자 지정 런타임 라이브러리에 대한 참조로 컴파일할 수 있습니다.  
  
 `path` 인수의 값이 DLL에 대해 정규화된 경로인 경우 컴파일러는 해당 파일을 런타임 라이브러리로 사용합니다. `path` 인수의 값이 DLL에 대해 정규화된 경로가 아닌 경우 Visual Basic 컴파일러는 먼저 현재 폴더에서 식별된 DLL을 검색합니다. 그런 다음, [-sdkpath](sdkpath.md) 컴파일러 옵션을 사용하여 지정한 경로를 검색합니다. `-sdkpath` 컴파일러 옵션을 사용하지 않으면 컴파일러는 .NET Framework 폴더(`%systemroot%\Microsoft.NET\Framework\versionNumber`)에서 식별된 DLL을 검색합니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 `-vbruntime` 옵션을 사용하여 사용자 지정 라이브러리에 대한 참조로 컴파일하는 방법을 보여줍니다.  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a>참조

- [Visual Basic Core – Visual Studio 2010 SP1의 새로운 컴파일 모드](https://devblogs.microsoft.com/vbteam/vb-core-new-compilation-mode-in-visual-studio-2010-sp1/)
- [Visual Basic 명령줄 컴파일러](index.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
- [-sdkpath](sdkpath.md)
