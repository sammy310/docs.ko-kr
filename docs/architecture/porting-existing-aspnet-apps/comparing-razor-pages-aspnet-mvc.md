---
title: Razor Pages와 ASP.NET MVC 비교
description: Razor Pages는 페이지 기반 앱에 대 한 기존 MVC 보기 보다 더 나은 책임을 구성 하는 방법을 제공 합니다. 이 섹션에서 일반적인 ASP.NET MVC 방법과 비교 하는 방법에 대해 알아봅니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: c188e7336e129fa710002081f1bef1f635cbe1fd
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401795"
---
# <a name="compare-razor-pages-to-aspnet-mvc"></a>Razor Pages와 ASP.NET MVC 비교

Razor Pages은 ASP.NET Core에서 페이지 또는 양식 기반 앱을 만드는 데 선호 되는 방법입니다. [문서](/aspnet/core/razor-pages/)에서 "Razor Pages는 컨트롤러 및 뷰를 사용 하는 것 보다 더 쉽고 생산성을 코딩 하는 페이지 중심 시나리오를 만들 수 있습니다." ASP.NET MVC 앱에서 뷰를 많이 사용 하는 경우 작업 및 보기에서 Razor Pages로 마이그레이션하는 것이 좋습니다.

일반적인 강력한 형식의 뷰 기반 MVC 앱은 하나 이상의 작업을 포함 하는 컨트롤러를 사용 합니다. 컨트롤러는 도메인 또는 데이터 모델과 상호 작용 하 고 viewmodel 클래스의 인스턴스를 만듭니다. 그러면이 viewmodel 클래스가 해당 작업과 연결 된 뷰로 전달 됩니다. MVC 앱의 기본 폴더 구조와 함께이 방법을 사용 하 여 앱에 새 페이지를 추가 하려면 한 폴더의 컨트롤러, 다른 폴더의 중첩 된 하위 폴더에 있는 보기 및 다른 폴더의 viewmodel을 수정 해야 합니다.

작업 (now *처리기*) 및 Viewmodel ( *PageModel* 라고 함)을 하나로 그룹화 하 고이 클래스를 뷰 (Razor 페이지)에 연결 Razor Pages. 모든 Razor Pages ASP.NET Core 프로젝트의 루트에 있는 *Pages* 폴더로 이동 합니다. 이 폴더의 이름 및 위치를 기반으로 하는 라우팅 규칙을 사용 Razor Pages 합니다. 처리기는 작업 메서드와 동일 하 게 동작 하지만 해당 이름 (예:)에서 처리 하는 HTTP 동사를 포함 합니다 `OnGet` . 또한 기본적으로 연결 된 페이지를 반환 하는 것으로 간주 되므로 반드시 반환 해야 하는 것은 아닙니다. 이는 동시에 Razor Pages 및 해당 처리기를 더 작고 더 집중 하 여 응용 프로그램의 특정 부분을 추가 하거나 수정 하는 데 필요한 모든 파일을 쉽게 찾고 작업할 수 있도록 하는 경향이 있습니다.

ASP.NET MVC에서 ASP.NET Core로 이동 하는 과정의 일부로 팀은 컨트롤러 및 뷰를 ASP.NET Core 컨트롤러와 뷰로 마이그레이션할지, Razor Pages로 마이그레이션할지를 고려해 야 합니다. 전자는 전반적으로 약간 낮은 노력을 기울여야 하지만 팀이 기존의 보기 기반 파일 구성에 대 한 Razor Pages 이점을 활용할 수 없습니다.

## <a name="references"></a>참조

- [ASP.NET Core의 Razor 페이지 소개](/aspnet/core/razor-pages/)
- [Razor Pages를 사용 하는 ASP.NET Core 앱 간소화](/archive/msdn-magazine/2017/september/asp-net-core-simpler-asp-net-mvc-apps-with-razor-pages)

>[!div class="step-by-step"]
>[이전](routing-differences.md)
>[다음](webapi-differences.md)
