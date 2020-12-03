---
title: '호환성이 손상되는 변경: Blazor: 정적 웹 자산에 대한 유효성 검사 논리를 업데이트함'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. Blazor: 정적 웹 자산에 대한 유효성 검사 논리를 업데이트함'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: f201818c0130739e8da4f42e7b1f3a1987f70d1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759728"
---
# <a name="blazor-updated-validation-logic-for-static-web-assets"></a>Blazor: 정적 웹 자산에 대한 유효성 검사 논리를 업데이트함

ASP.NET Core 3.1 및 Blazor WebAssembly 3.2에서 정적 웹 자산에 대한 충돌 유효성 검사에 문제가 있습니다. 문제:

* 호스트 자산과 RCL(Razor 클래스 라이브러리) 및 Blazor WebAssembly 앱의 자산 간의 적절한 충돌 검색을 방지했습니다.
* 기본적으로 RCL의 정적 웹 자산은 `_content/$(PackageId)` 접두사 아래에 제공되므로 대부분 Blazor WebAssembly 앱에 영향을 줍니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="old-behavior"></a>이전 동작

개발하는 동안 RCL의 정적 웹 자산은 동일한 호스트 경로에 있는 호스트 프로젝트 자산으로 자동으로 재정의할 수 있습니다. */folder/file.txt* 에서 제공되도록 정적 웹 자산을 정의한 RCL을 생각해 보세요. 호스트가 파일을 *wwwroot/folder/file.txt* 에 배치한 경우 서버의 파일은 RCL 또는 Blazor WebAssembly 앱의 파일을 자동을 재정의했습니다.

## <a name="new-behavior"></a>새 동작

이 문제가 발생하면 ASP.NET Core에서 올바르게 감지합니다. 적절한 조치를 취할 수 있도록 사용자에게 충돌에 대해 알립니다.

## <a name="reason-for-change"></a>변경 이유

정적 웹 자산은 프로젝트의 *wwwroot* 호스트에 있는 파일로 재정의할 수 없습니다. 이러한 파일의 재정의를 허용하면 진단하기 어려운 오류가 발생할 수 있습니다. 따라서 게시된 앱에서 정의되지 않은 동작 변경이 발생할 수 있습니다.

## <a name="recommended-action"></a>권장 조치

기본적으로 RCL 파일은 호스트의 파일과 충돌할 이유가 없습니다. RCL 파일에는 `_content/${PackageId}` 접두사가 붙습니다. Blazor WebAssembly 파일은 호스트 URL 공간의 루트에 배치되어 충돌이 더 쉽게 발생할 수 있습니다. 예를 들어 Blazor WebAssembly 앱에는 *wwwroot* 폴더에도 포함될 수 있는 *favicon.ico* 파일이 포함되어 있습니다.

충돌의 소스가 RCL 파일이면 코드가 라이브러리의 자산을 프로젝트의 *wwwroot* 폴더로 복사하고 있음을 의미하는 경우가 많습니다. 파일을 복사하는 코드를 작성하면 정적 웹 자산의 주요 목표에서 벗어납니다. 이 목표는 콘텐츠가 업데이트될 때 새 컴파일을 트리거하지 않고 브라우저에서 업데이트를 가져오는 데 기본이 됩니다.

이 동작을 유지하고 호스트에 파일을 유지하도록 선택할 수 있습니다. 이렇게 하려면 사용자 지정 MSBuild 대상을 사용하여 정적 웹 자산 목록에서 파일을 제거합니다.

호스트 프로젝트의 파일 대신 RCL의 파일이나 Blazor WebAssembly 앱의 파일을 사용하려면 호스트 프로젝트에서 파일을 제거합니다.

## <a name="affected-apis"></a>영향을 받는 API

None

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
