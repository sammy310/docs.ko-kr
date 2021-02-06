---
description: '자세한 정보: WCF 라이브러리 프로젝트 배포'
title: WCF 라이브러리 프로젝트 배포
ms.date: 03/30/2017
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
ms.openlocfilehash: 1476f564e3e341c77ab9ba4e4281d6f242a735cd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646103"
---
# <a name="deploying-a-wcf-library-project"></a>WCF 라이브러리 프로젝트 배포

이 항목에서는 WCF (Windows Communication Foundation) 서비스 라이브러리 프로젝트를 배포할 수 있는 방법에 대해 설명 합니다.  
  
## <a name="deploying-a-wcf-service-library"></a>WCF 서비스 라이브러리 배포  

 WCF 서비스 라이브러리는 DLL (동적 연결 라이브러리)입니다. 따라서 자체적으로 실행될 수 없으며 호스팅 환경에서 배포되어야 합니다. 이 프로세스에 대 한 자세한 내용은 [WCF 서비스 호스팅 및](/previous-versions/dotnet/articles/bb332338(v=msdn.10))사용을 참조 하세요.  
  
 WCF 서비스 라이브러리는 다른 WCF 서비스와 마찬가지로 배포할 수 있습니다. 그러나 .NET Framework는 Dll에 대 한 구성을 지원 하지 않습니다. <xref:System.Configuration>은 응용 프로그램 도메인당 하나의 구성 파일을 지원합니다. WCF 서비스 라이브러리 프로젝트는 개발 중에 라이브러리에 대 한 App.config 파일을 제공 하 여 이러한 제한을 완화 합니다. 그러나 App.config 파일은 배포 후에 인식되지 않습니다.  
  
 구성 코드를 호스팅 환경에서 인식하는 구성 파일로 이동해야 합니다. 자체 호스팅의 경우 App.config 파일의 내용을 호스팅 실행 파일의 App.config 파일에 복사해야 합니다. IIS를 사용하여 서비스를 호스팅하려면 App.config 파일의 내용을 가상 디렉터리의 Web.config 파일에 복사해야 합니다.
