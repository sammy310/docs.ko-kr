---
title: .NET Framework의 보안 변경 내용
ms.date: 03/30/2017
helpviewer_keywords:
- Allow Partially Trusted Callers attribute
- .NET Framework 4, security changes
- .NET Framework security
- security-transparent code
- security-critical code
- code access security, changes
ms.assetid: 5e87881c-9c13-4b52-8ad1-e34bb46e8aaa
author: mairaw
ms.author: mairaw
ms.openlocfilehash: af2869e5ca3b41778c094b7a78a9493e74868811
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204501"
---
# <a name="security-changes-in-the-net-framework"></a>.NET Framework의 보안 변경 내용

The most important change to security in the .NET Framework 4.5 is in strong naming. 변경에 대한 설명은 [Enhanced Strong Naming](../../standard/assembly/enhanced-strong-naming.md) 을 참조하세요.  
  
.NET Framework는 관리되는 애플리케이션에 대한 2계층 보안 모델을 제공합니다. Windows 8.x Store apps run in a Windows security container that limits access to resources. 해당 컨테이너 내에서 관리되는 애플리케이션은 완전히 신뢰할 수 있는 상태로 실행됩니다. CAS(코드 액세스 보안) 측면에서 개발자가 권한을 높이기 위해 수행할 수 있는 작업이 없습니다. Windows에서 부여된 권한에 대한 자세한 내용은 Windows 개발자 센터의 [앱 기능 선언(Windows 스토어 앱)](https://go.microsoft.com/fwlink/?LinkId=230436) 을 참조하세요. For information about creating a Windows 8.x Store app, see [Create your first Windows Store app using C# or Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).
