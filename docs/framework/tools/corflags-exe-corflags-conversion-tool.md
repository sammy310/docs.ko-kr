---
title: CorFlags.exe(CorFlags 변환 도구)
description: CorFlags.exe 즉, CorFlags 변환 도구를 이해합니다. 이 도구를 사용하면 이식 가능한 실행 이미지 헤더의 CorFlags 섹션을 구성할 수 있습니다.
ms.date: 03/30/2017
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
ms.openlocfilehash: 4481e6718372fe7b58dbc05ab7cfe35e6d3047ce
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102258054"
---
# <a name="corflagsexe-corflags-conversion-tool"></a>CorFlags.exe(CorFlags 변환 도구)

CorFlags 변환 도구를 사용하면 이식할 수 있는 실행 가능 이미지 헤더의 CorFlags 섹션을 구성할 수 있습니다.  
  
 이 도구는 자동으로 Visual Studio와 함께 설치됩니다. 도구를 실행하려면 [개발자용 명령줄 셸](/visualstudio/ide/reference/command-prompt-powershell)을 사용합니다.  
  
 명령 프롬프트에 다음을 입력합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
CorFlags.exe assembly [options]  
```  
  
## <a name="parameters"></a>매개 변수  
  
|필수적 매개 변수|설명|  
|------------------------|-----------------|  
|`assembly`|CorFlags를 구성할 어셈블리의 이름입니다.|  
  
|옵션|Description|  
|:------------|-----------------|  
|`-32BIT[REQ]+`|32BITREQUIRED 플래그를 설정합니다.|  
|`-32BIT[REQ]-`|32BITREQUIRED 플래그를 지웁니다.|  
|`-32BITPREF+`|32BITPREFERRED 플래그를 설정합니다. 응용 프로그램이 64비트 플랫폼에서 32비트 프로세스로 실행됩니다. EXE 파일에만 이 플래그를 설정합니다. DLL에 플래그가 설정되면 DLL은 64비트 프로세스 로드에 실패하고 <xref:System.BadImageFormatException> 예외가 throw됩니다. 이 플래그를 사용하여 EXE 파일은 64비트 프로세스에 로드할 수 있습니다.<br /><br /> .NET Framework 4.5의 새로운 기능입니다.|  
|`-32BITPREF-`|32BITPREFERRED 플래그를 지웁니다.<br /><br /> .NET Framework 4.5의 새로운 기능입니다.|  
|`-?`|이 도구의 명령 구문 및 옵션을 표시합니다.|  
|`-Force`|어셈블리의 이름이 강력한 이름인 경우에도 업데이트합니다. **중요:**  강력한 이름의 어셈블리를 업데이트하면 코드를 실행하기 전에 다시 서명해야 합니다.|  
|`-help`|이 도구의 명령 구문 및 옵션을 표시합니다.|  
|`-ILONLY+`|ILONLY 플래그를 설정합니다.|  
|`-ILONLY-`|ILONLY 플래그를 지웁니다.|  
|`-nologo`|Microsoft 시작 배너를 표시하지 않습니다.|  
|`-RevertCLRHeader`|CLR 헤더 버전을 2.0으로 되돌립니다.|  
|`-UpgradeCLRHeader`|CLR 헤더 버전을 2.5로 업그레이드합니다. **참고:**  기본적으로 어셈블리를 실행하려면 CLR 헤더 버전이 2.5 이상이어야 합니다.|  
  
## <a name="remarks"></a>설명  

 옵션을 지정하지 않으면 CorFlags 변환 도구에서 지정한 어셈블리에 대한 플래그를 표시합니다.  
  
## <a name="see-also"></a>참조

- [도구](index.md)
- [64비트 애플리케이션](../64-bit-apps.md)
- [개발자 명령줄 셸](/visualstudio/ide/reference/command-prompt-powershell)
