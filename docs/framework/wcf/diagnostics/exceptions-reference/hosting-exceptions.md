---
description: '자세한 정보: 예외 호스팅'
title: 호스팅 예외
ms.date: 03/30/2017
ms.assetid: ad9e14f8-fa17-4d59-b365-fe0e7ec17c98
ms.openlocfilehash: ba2ff3d4bd069483ddc620a09bb97eeaddf84a56
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686455"
---
# <a name="hosting-exceptions"></a>호스팅 예외

이 항목에서는 호스팅에 의해 생성된 모든 예외를 보여 줍니다.  
  
## <a name="exception-list"></a>예외 목록  
  
|리소스 코드|리소스 문자열|  
|-------------------|---------------------|  
|Hosting_AddressIsAbsoluteUri|전체 URI가 허용되지 않습니다. ServiceHostingEnvironment.EnsureServiceAvailable API에는 전체 URI가 허용되지 않습니다. 해당 서비스의 가상 경로를 사용하십시오.|  
|Hosting_BuildProviderCouldNotCreateType|서비스를 컴파일하는 동안 지정된 CLR 형식을 로드할 수 없습니다. 이 형식이 응용 프로그램의 \\ \bin 디렉터리에 있는 컴파일된 어셈블리에 포함 되어 \\ 있거나 전역 어셈블리 캐시에 설치 된 어셈블리에 있는 소스 App_Code 파일에 정의 되어 있는지 확인 하십시오. 형식 이름은 대/소문자를 구분합니다. \\\ App_Code 및 \bin과 같은 디렉터리는 \\ 응용 프로그램의 루트 디렉터리에 있어야 합니다. \\\ App_Code 및 \\ \bin 디렉터리는 하위 디렉터리에 중첩 될 수 없습니다.|
