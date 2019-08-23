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
ms.openlocfilehash: 25368d23c398fb3674d5c2d75d4997f917a1c3d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937349"
---
# <a name="-sdkpath"></a>-sdkpath
Mscorlib.dll 및 Microsoft.visualbasic의 위치를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-sdkpath:path  
```  
  
## <a name="arguments"></a>인수  
 `path`  
 컴파일에 사용할 mscorlib.dll 및 Microsoft.visualbasic 버전을 포함 하는 디렉터리입니다. 이 경로는 로드 될 때까지 확인 되지 않습니다. 공백을 포함 하는 경우 디렉터리 이름을 큰따옴표 ("")로 묶습니다.  
  
## <a name="remarks"></a>설명  
 이 옵션은 Visual Basic 컴파일러가 기본 위치가 아닌 위치에서 mscorlib.dll 및 Microsoft.visualbasic 파일을 로드 하도록 지시 합니다. 옵션 `-sdkpath` 은 [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)와 함께 사용 하도록 설계 되었습니다. .NET Compact Framework는 이러한 지원 라이브러리의 다른 버전을 사용 하 여 장치에서 찾을 수 없는 형식 및 언어 기능을 사용 하지 않습니다.  
  
> [!NOTE]
> 이 `-sdkpath` 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다. 이 `-sdkpath` 옵션은 Visual Basic 장치 프로젝트가 로드 될 때 설정 됩니다.  
  
 컴파일러 옵션을 사용 하 `-vbruntime` 여 컴파일러에서 Visual Basic 런타임 라이브러리에 대 한 참조 없이 컴파일하도록 지정할 수 있습니다. 자세한 내용은 [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)을 참조 하세요.  
  
## <a name="example"></a>예제  
 다음 코드는 C `Myfile.vb` 드라이브에 있는 .NET Compact Framework의 기본 설치 디렉터리에 있는 mscorlib.dll 및 microsoft.visualbasic 버전을 사용 하 여 .NET Compact Framework로 컴파일합니다. 일반적으로 .NET Compact Framework의 최신 버전을 사용 합니다.  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)
- [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
