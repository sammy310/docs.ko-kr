---
title: ASP.NET MVC 및 ASP.NET Core에서 정적 파일을 제공 합니다.
description: IIS의 ASP.NET MVC와 비교 하 여 ASP.NET Core에서 정적 파일을 제공 하기 위한 지원을 구성 하는 데 관련 된 사항은 무엇입니까?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 02f84a6985835502c24db8cc68db24c8de086b18
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401700"
---
# <a name="serve-static-files-in-aspnet-mvc-and-aspnet-core"></a>ASP.NET MVC 및 ASP.NET Core에서 정적 파일을 제공 합니다.

대부분의 웹 앱은 클라이언트에 있는 그대로 전송 되어야 하는 서버측 논리와 정적 파일의 조합을 포함 하 고 있습니다. ASP.NET MVC에서 정적 파일을 처리 하는 ASP.NET Core 처리 하는 방법은 무엇입니까?

## <a name="host-static-files-in-aspnet-mvc"></a>ASP.NET MVC에서 정적 파일 호스트

IIS에서 호스트 되는 ASP.NET MVC 앱은 일반적으로 앱에서 직접 정적 파일을 호스팅합니다. ASP.NET MVC는 서버에서 전용으로 유지 해야 하는 파일을 사용 하 여 정적 파일을 나란히 배치할 수 있도록 지원 합니다. IIS 및 ASP.NET는 특정 파일 또는 파일 확장명이 ASP.NET 앱이 호스트 되는 폴더에서 제공 되는 것을 명시적으로 제한 해야 합니다.

많은 정적 파일의 경우 CDN (content delivery network)을 사용 하는 것이 좋습니다. [정적 콘텐츠 호스팅을](/azure/architecture/patterns/static-content-hosting) 사용 하면 앱 서버에서 로드와 대역폭을 줄이는 동시에 성능을 향상 시킬 수 있습니다.

## <a name="host-static-files-in-aspnet-core"></a>ASP.NET Core에서 정적 파일 호스트

이는 놀라운 것일 수 있지만 ASP.NET Core는 정적 파일에 대 한 기본 제공 지원을 제공 하지 않습니다. IIS에서 사용 하는 ASP.NET의 일부로 항상 존재 하는이 기능은 ASP.NET Core 또는 Kestrel 웹 서버에 내장 되지 않습니다. ASP.NET Core 앱에서 정적 파일을 제공 하려면 [정적 파일 미들웨어](/aspnet/core/fundamentals/static-files)를 구성 해야 합니다.

정적 파일 미들웨어가 구성 된 상태에서 ASP.NET Core 앱은 특정 폴더 (일반적으로 */wwwroot*)에 있는 모든 파일을 제공 합니다. 응용 프로그램 또는 프로젝트 폴더의 다른 파일은 실수로 서버에 의해 노출 될 위험이 있습니다. IIS의 경우와 마찬가지로 파일 이름 또는 확장명을 기반으로 하는 특별 한 제한 사항은 구성 해야 합니다. 대신 개발자가 파일을 *wwwroot* 폴더에 배치할 때 파일을 공개적으로 노출 하도록 명시적으로 선택 합니다. 기본적으로이 폴더의 외부에 있는 파일은 공유 되지 않습니다.

정적 파일에 대 한 지원은 미들웨어를 사용 하기 때문에 다른 미들웨어는 동일한 요청 파이프라인의 일부로 적용할 수 있습니다. 미들웨어의 예로는 인증, 캐싱 및 압축이 있습니다.

물론 ASP.NET MVC 앱에서 사용 되는 것과 동일한 모든 이유로 CDNs는 ASP.NET Core 앱에 적합 합니다. .NET Core로의 마이그레이션을 준비 하는 과정에서 앱이 CDN을 사용 하 여 실현할 수 있는 이점이 있으면 .NET Core로 마이그레이션하기 전에 CDN으로 정적 파일을 이동 하는 것이 좋습니다. 이렇게 하면 정적 자산의 전체 마이그레이션 작업 범위가 줄어듭니다.

## <a name="references"></a>참조

- [정적 콘텐츠 호스팅](/azure/architecture/patterns/static-content-hosting)
- [ASP.NET Core의 정적 파일](/aspnet/core/fundamentals/static-files)

>[!div class="step-by-step"]
>[이전](hosting-differences.md)
>[다음](dependency-injection-differences.md)
