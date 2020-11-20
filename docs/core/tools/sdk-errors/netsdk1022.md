---
title: 'NETSDK1022: 중복 항목이 포함되었습니다.'
description: 기본 포함 내용에 따라 중복 항목 메시지를 해결하는 방법입니다.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1022
ms.openlocfilehash: bc803f5316bf09c12c563f1a63b8385d1be4e9ce
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506638"
---
# <a name="netsdk1022-duplicate-items-were-included"></a><span data-ttu-id="f4592-103">NETSDK1022: 중복 항목이 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f4592-103">NETSDK1022: Duplicate items were included.</span></span>

<span data-ttu-id="f4592-104">**이 문서의 적용 대상:** ✔️ .NET 2.1.100 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="f4592-104">**This article applies to:** ✔️ .NET 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="f4592-105">Visual Studio 2017/MSBuild 버전 15.3부터 .NET SDK는 기본적으로 프로젝트 디렉터리의 항목을 자동으로 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f4592-105">Starting in Visual Studio 2017 / MSBuild version 15.3, the .NET SDK automatically includes items from the project directory by default.</span></span>  <span data-ttu-id="f4592-106">여기에는 `Compile` 및 `Content` 대상이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4592-106">This includes `Compile` and `Content` targets.</span></span>  <span data-ttu-id="f4592-107">따라서 프로젝트 파일을 많이 정리하여 복잡성을 줄여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4592-107">This should greatly clean up your project file and reduce the complexity you have there.</span></span>

<span data-ttu-id="f4592-108">올바른 속성을 false로 설정하여 이전 동작으로 되돌릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4592-108">You can revert to the earlier behavior by setting the correct property to false.</span></span>

<span data-ttu-id="f4592-109">`Compile` 항목에 대한 예제:</span><span class="sxs-lookup"><span data-stu-id="f4592-109">Example for `Compile` items:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
