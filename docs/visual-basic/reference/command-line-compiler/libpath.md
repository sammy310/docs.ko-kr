---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: dff7e0c3eb696b9b18f4c4e59240a26c1cb9782c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408551"
---
# <a name="-libpath"></a>-libpath
참조된 어셈블리의 위치를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-libpath:dirList  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`dirList`|필수 요소. 참조된 어셈블리를 현재 작업 디렉터리(컴파일러를 호출하는 디렉터리) 또는 공용 언어 런타임의 시스템 디렉터리에서 찾을 수 없는 경우 컴파일러에서 확인할 세미콜론으로 구분된 디렉터리 목록입니다. 디렉터리 이름에 공백이 있으면 이름을 따옴표(" ")로 묶습니다.|  
  
## <a name="remarks"></a>설명  
 `-libpath` 옵션은 [-reference](reference.md) 옵션에서 참조하는 어셈블리의 위치를 지정합니다.  
  
 컴파일러는 정규화되지 않은 어셈블리 참조를 다음 순서대로 검색합니다.  
  
1. 현재 작업 디렉터리입니다. 컴파일러가 호출되는 디렉터리입니다.  
  
2. 공용 언어 런타임 시스템 디렉터리입니다.  
  
3. `-libpath`로 지정된 디렉터리입니다.  
  
4. LIB 환경 변수로 지정된 디렉터리입니다.  
  
 `-libpath` 옵션은 가감되므로 두 번 이상 지정하면 이전 값에 추가됩니다.  
  
 `-reference`를 사용하여 어셈블리 참조를 지정합니다.  
  
|Visual Studio 통합 개발 환경에서 -libpath를 설정하려면 다음을 수행합니다.|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다. <br />2.  **참조** 탭을 클릭합니다.<br />3.  **참조 경로...** 단추를 클릭합니다.<br />4.  **참조 경로** 대화 상자의 **Folder:** 상자에 디렉터리 이름을 입력합니다.<br />5.  **폴더 추가**를 클릭합니다.|  
  
## <a name="example"></a>예제  
 다음 코드는 `T2.vb`를 컴파일하여 .exe 파일을 만듭니다. 컴파일러는 작업 디렉터리, C: 드라이브의 루트 디렉터리 및 C: 드라이브의 새 어셈블리 디렉터리에서 어셈블리 참조를 찾습니다.  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a>참조

- [.NET 어셈블리](../../../standard/assembly/index.md)
- [Visual Basic 명령줄 컴파일러](index.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
