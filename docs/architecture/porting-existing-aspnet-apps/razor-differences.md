---
title: ASP.NET MVC 및 ASP.NET Core에서 Razor 사용 비교
description: ASP.NET MVC와 ASP.NET Core에서 Razor는 어떻게 다릅니까?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: a9f7fa2e6b8c0c6bf61c743cf8c956b1ad09713c
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401718"
---
# <a name="compare-razor-usage-in-aspnet-mvc-and-aspnet-core"></a>ASP.NET MVC 및 ASP.NET Core에서 Razor 사용 비교

ASP.NET MVC와 ASP.NET Core 간에 Razor의 기본 구문이 크게 변경 되지 않았습니다. 그러나 마이그레이션할 때 고려해 야 하는 [태그 도우미](/aspnet/core/mvc/views/tag-helpers/intro) 및 Razor Pages의 소개와 같은 몇 가지 차이점이 있습니다. 앱이 사용자 지정 Razor 기능을 과도 하 게 사용 하는 경우 [ASP.NET Core에 대 한 Razor 구문 참조](/aspnet/core/razor-pages) 를 참조 하 여 ASP.NET Core로 마이그레이션할 때 필요한 변경 내용을 확인 합니다.

## <a name="tag-helpers"></a>태그 도우미

태그 도우미를 사용하면 서버 쪽 코드를 Razor 파일에서 HTML 요소를 만들고 렌더링하는 데 사용할 수 있습니다. HTML 도우미에 비해 많은 이점을 제공 하므로 가능 하면 HTML 도우미 대신 사용 해야 합니다. Html에 친숙 한 개발 환경을 제공 합니다. 표준 HTML 처럼 보이지만 HTML 편집을 위해 디자인 된 대부분의 도구에서 무시 되기 때문입니다. _Visual Studio_ 내에는 태그 도우미를 사용 하 여 HTML 및 Razor 태그를 만들기 위한 다양 한 IntelliSense 지원이 있습니다. 태그 도우미는 Razor 파일의 선언 태그에서 단순 하거나 복잡 한 동작을 제공할 수 있습니다.

## <a name="razor-pages"></a>Razor 페이지

Razor Pages는 페이지 및 양식 기반 앱에 대 한 컨트롤러, 작업 및 보기에 대 한 대안을 제공 합니다. [이 장 앞부분의 ASP.NET MVC와 Razor Pages 되었습니다](./comparing-razor-pages-aspnet-mvc.md).

## <a name="references"></a>참조

- [ASP.NET MVC에서 ASP.NET Core MVC: 컨트롤러 및 뷰로 마이그레이션](/aspnet/core/migration/mvc#migrate-controllers-and-views)
- [ASP.NET Core의 태그 도우미](/aspnet/core/mvc/views/tag-helpers/intro)
- [ASP.NET Core의 Razor 페이지 소개](/aspnet/core/razor-pages)
- [ASP.NET Core에 대한 Razor 구문 참조](/aspnet/core/razor-pages)

>[!div class="step-by-step"]
>[이전](controller-differences.md)
>[다음](signalr-differences.md)
