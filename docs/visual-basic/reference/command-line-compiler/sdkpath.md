---
title: -sdkpath
ms.date: 07/20/2015
f1_keywords:
- sdkpath
- -sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
ms.openlocfilehash: 18bf22861c1cbc3a37ef917b421491c2d01efba8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085115"
---
# <a name="-sdkpath"></a>-sdkpath

mscorlib.dll 및 Microsoft.VisualBasic.dll의 위치를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-sdkpath:path  
```  
  
## <a name="arguments"></a>인수  

 `path`  
 컴파일에 사용할 mscorlib.dll 및 Microsoft.VisualBasic.dll 버전을 포함하는 디렉터리입니다. 이 경로는 로드될 때까지 확인되지 않습니다. 공백이 있으면 디렉터리 이름을 따옴표(" ")로 묶습니다.  
  
## <a name="remarks"></a>설명  

 이 옵션은 Visual Basic 컴파일러가 기본 위치가 아닌 위치에서 mscorlib.dll 및 Microsoft.VisualBasic.dll 파일을 로드하도록 지시합니다. `-sdkpath` 옵션은 [-netcf](netcf.md)와 함께 사용하도록 설계되었습니다. .NET Compact Framework는 이러한 지원 라이브러리의 다른 버전을 사용하여 디바이스에 없는 형식 및 언어 기능을 사용하지 않습니다.  
  
> [!NOTE]
> Visual Studio 개발 환경 내에서는 `-sdkpath` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다. `-sdkpath` 옵션은 Visual Basic 디바이스 프로젝트가 로드될 때 설정됩니다.  
  
 `-vbruntime` 컴파일러 옵션을 사용하여 컴파일러가 Visual Basic 런타임 라이브러리에 대한 참조 없이 컴파일하도록 지정할 수 있습니다. 자세한 내용은 [-vbruntime](vbruntime.md)을 참조하세요.  
  
## <a name="example"></a>예제  

 다음 코드는 C 드라이브의 .NET Compact Framework 기본 설치 디렉터리에 있는 Mscorlib.dll 및 Microsoft.VisualBasic.dll 버전을 사용하여 .NET Compact Framework로 `Myfile.vb`를 컴파일합니다. 일반적으로 최신 버전의 .NET Compact Framework를 사용합니다.  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
- [-netcf](netcf.md)
- [-vbruntime](vbruntime.md)
