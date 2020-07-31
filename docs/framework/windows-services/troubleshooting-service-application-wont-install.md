---
title: '문제 해결: 서비스 애플리케이션이 설치되지 않음'
description: 서비스 애플리케이션이 설치되지 않을 경우 문제 해결을 수행합니다. 서비스 클래스의 ServiceName 속성이 올바르게 설정되어 있는지 확인합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
author: ghogen
ms.openlocfilehash: 4a57fb6975a6ded48abf7c8fd7eacec16e4f94d8
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925529"
---
# <a name="troubleshooting-service-application-wont-install"></a>문제 해결: 서비스 애플리케이션이 설치되지 않음
서비스 애플리케이션이 올바로 설치되지 않으면 서비스 클래스의 <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> 속성이 해당 서비스의 설치 관리자에 표시된 값과 동일하게 설정되어 있는지 확인합니다. 서비스가 올바로 설치되려면 이 값이 두 인스턴스 모두에서 동일해야 합니다.  
  
> [!NOTE]
> 설치 로그를 확인하여 설치 프로세스에 대한 피드백을 얻을 수도 있습니다.  
  
 같은 이름의 다른 서비스가 이미 설치되어 있는지도 확인해야 합니다. 서비스 이름이 고유해야만 설치될 수 있습니다.  
  
## <a name="see-also"></a>참조

- [Windows 서비스 애플리케이션 소개](introduction-to-windows-service-applications.md)
