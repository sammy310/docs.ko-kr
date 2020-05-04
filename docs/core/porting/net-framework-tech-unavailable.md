---
title: .NET Core에서 사용할 수 없는 .NET Framework 기술
titleSuffix: ''
description: .NET Core에서 사용할 수 없는 .NET Framework 기술에 대해 알아보기
author: cartermp
ms.date: 04/30/2019
ms.openlocfilehash: f95205330837551085b8f58dfbdfcd702356c98f
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506833"
---
# <a name="net-framework-technologies-unavailable-on-net-core"></a>.NET Core에서 사용할 수 없는 .NET Framework 기술

.NET Framework 라이브러리에서 사용할 수 있는 AppDomain, 원격, CAS(코드 액세스 보안), 보안 투명도, System.EnterpriseServices 같은 몇몇 기술은 .NET Core에서 사용할 수 없습니다. 라이브러리가 이러한 기술 중 하나 이상에 의존하는 경우 아래에 설명된 대체 방법을 고려하세요. API 호환성에 대한 자세한 내용은 [.NET Core 호환성이 손상되는 변경 사항](../compatibility/breaking-changes.md)을 참조하세요.

API 또는 기술이 현재 구현되지 않았기 때문에 이들을 고의로 지원하지 않는 것은 아닙니다. 특정 문제가 의도적으로 발생하는 것인지 확인하려면 .NET Core용 GitHub 리포지토리를 검색합니다. 이를 찾지 못한 경우 [dotnet/runtime 리포지토리](https://github.com/dotnet/runtime/issues)에 이슈를 보고하고 특정 API 및 기술을 요청하세요.

## <a name="appdomains"></a>AppDomain

애플리케이션 도메인(AppDomains)은 앱을 서로 분리합니다. AppDomain에는 런타임 지원이 필요하며 일반적으로 비용이 많이 듭니다. 추가 앱 도메인을 만드는 것은 지원되지 않으며 향후 이 기능을 추가할 계획은 없습니다. 코드 격리의 경우 별도의 프로세스 또는 컨테이너를 대신 사용하세요. 어셈블리를 동적으로 로드하려면 <xref:System.Runtime.Loader.AssemblyLoadContext> 클래스를 사용합니다.

.NET Framework에서 코드를 쉽게 마이그레이션할 수 있도록 .NET Core에서는 <xref:System.AppDomain> API 표면의 일부를 공개했습니다. API 중 일부는 정상적으로 작동하고(예: <xref:System.AppDomain.UnhandledException?displayProperty=nameWithType>), 일부 멤버는 아무것도 수행하지 않고(예: <xref:System.AppDomain.SetCachePath%2A>), 일부는 <xref:System.PlatformNotSupportedException>을 throw합니다(예: <xref:System.AppDomain.CreateDomain%2A>). [dotnet/runtime GitHub 리포지토리](https://github.com/dotnet/runtime)의 [`System.AppDomain` 참조 소스](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Private.CoreLib/src/System/AppDomain.cs)에 대해 사용하는 유형을 확인합니다. 구현된 버전과 일치하는 분기를 선택해야 합니다.

## <a name="remoting"></a>원격 통신

.NET Remoting은 문제가 있는 아키텍처로 확인되었으며 더 이상 지원되지 않는 AppDomain 간 통신에 사용됩니다. 또한 원격 통신에는 유지 관리 비용이 많이 드는 런타임 지원이 필요합니다. 이러한 이유로 .NET Remoting은 .NET Core에서 지원되지 않으며 향후 지원을 추가할 계획이 없습니다.

프로세스 간 통신을 위해 <xref:System.IO.Pipes> 클래스 또는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> 클래스 같은 IPC(Inter-process communication) 메커니즘을 원격 통신 대신 사용할 수 있습니다.

여러 컴퓨터에서 네트워크 기반 솔루션을 대신 사용하세요. HTTP와 같이 오버헤드가 낮은 일반 텍스트 프로토콜을 사용하는 것이 좋습니다. ASP.NET Core에서 사용하는 웹 서버인 [Kestrel 웹 서버](/aspnet/core/fundamentals/servers/kestrel)도 옵션이 될 수 있습니다. 또한 네트워크 기반, 컴퓨터 간 시나리오에서 <xref:System.Net.Sockets>의 사용을 고려하세요. 추가 옵션은 [.NET 오픈 소스 개발자 프로젝트: 메시징](https://github.com/Microsoft/dotnet/blob/master/dotnet-developer-projects.md#messaging)을 참조하세요.

## <a name="code-access-security-cas"></a>CAS(코드 액세스 보안)

관리형 애플리케이션 또는 라이브러리에서 사용하거나 실행하는 리소스를 제한하기 위해 런타임 또는 프레임워크에 의존하는 샌드박싱은 [.NET Framework에서 지원되지 않으므로](../../framework/misc/code-access-security.md) .NET Core에서도 지원되지 않습니다. .NET Framework 및 런타임에는 CAS를 보안 경계로 계속 처리하기 위해 권한 상승이 발생하는 사례가 너무 많이 있습니다. 또한 CAS는 구현을 더욱 복잡하게 만들고 이를 사용하지 않을 애플리케이션의 정확성-성능에 종종 영향을 미칩니다.

최소한의 권한으로 프로세스를 실행하기 위해 가상화, 컨테이너 또는 사용자 계정과 같은 운영 체제에서 제공되는 보안 경계를 사용할 수 있습니다.

## <a name="security-transparency"></a>보안 투명도

CAS와 마찬가지로 보안 투명도는 샌드박스 코드를 보안상 중요한 코드와 선언적인 방식으로 분리할 수 있지만 [더 이상 보안 경계로서 지원되지는 않습니다](../../framework/misc/security-transparent-code.md). 이 기능은 Silverlight에서 많이 사용됩니다.

최소한의 권한으로 프로세스를 실행하려면 가상화, 컨테이너 또는 사용자 계정과 같은 운영 체제에서 제공하는 보안 경계를 사용할 수 있습니다.

## <a name="systementerpriseservices"></a>System.EnterpriseServices

System.EnterpriseServices(COM+)는 .NET Core에서 지원되지 않습니다.

## <a name="see-also"></a>참조

- [.NET Framework에서 .NET Core로의 이식 개요](../porting/index.md)
