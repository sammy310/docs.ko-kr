---
ms.openlocfilehash: 418bcdca1e9a325894891d7b0e080ce035e2d1b4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614683"
---
### <a name="aspnet-accessibility-improvements-in-net-framework-471"></a><span data-ttu-id="7d89d-101">.NET Framework 4.7.1의 ASP.NET 액세스 가능성 향상</span><span class="sxs-lookup"><span data-stu-id="7d89d-101">ASP.NET Accessibility Improvements in .NET Framework 4.7.1</span></span>

#### <a name="details"></a><span data-ttu-id="7d89d-102">설명</span><span class="sxs-lookup"><span data-stu-id="7d89d-102">Details</span></span>

<span data-ttu-id="7d89d-103">.NET Framework 4.7.1부터 ASP.NET은 ASP.NET 웹 컨트롤이 Visual Studio의 액세스 가능성 기술과 연동하는 방식을 개선하여 ASP.NET 고객을 보다 잘 지원하도록 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7d89d-103">Starting with the .NET Framework 4.7.1, ASP.NET has improved how ASP.NET Web Controls work with accessibility technology in Visual Studio to better support ASP.NET customers.</span></span>  <span data-ttu-id="7d89d-104">여기에는 다음과 같은 변경이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d89d-104">These include the following changes:</span></span>

- <span data-ttu-id="7d89d-105">자세히 보기 마법사의 필드 추가 대화 상자 또는 ListView 마법사의 ListView 구성 대화 상자와 같이 컨트롤에서 누락된 UI 액세스 가능성 패턴을 구현하도록 변경됨.</span><span class="sxs-lookup"><span data-stu-id="7d89d-105">Changes to implement missing UI accessibility patterns in controls, like the Add Field dialog in the Details View wizard, or the Configure ListView dialog of the ListView wizard.</span></span>
- <span data-ttu-id="7d89d-106">데이터 호출기 필드 편집기와 같이 고대비 모드에서 디스플레이를 개선하도록 변경됨.</span><span class="sxs-lookup"><span data-stu-id="7d89d-106">Changes to improve the display in High Contrast mode, like the Data Pager Fields Editor.</span></span>
- <span data-ttu-id="7d89d-107">DataPager 컨트롤의 [호출기 필드 편집] 마법사의 [필드] 대화 상자, [ObjectContext 구성] 대화 상자 또는 [데이터 원본 구성] 마법사의 [데이터 선택 구성] 대화 상자와 같은 컨트롤의 키보드 탐색 환경을 개선하도록 변경됨.</span><span class="sxs-lookup"><span data-stu-id="7d89d-107">Changes to improve the keyboard navigation experiences for controls, like the Fields dialog in the Edit Pager Fields wizard of the DataPager control, the Configure ObjectContext dialog, or the Configure Data Selection dialog of the Configure Data Source wizard.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7d89d-108">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="7d89d-108">Suggestion</span></span>

<span data-ttu-id="7d89d-109">**이러한 변경을 선택/해제하는 방법** Visual Studio 디자이너에서 이러한 변경의 이점을 얻으려면 .NET Framework 4.7.1 이상에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d89d-109">**How to opt in or out of these changes** In order for the Visual Studio Designer to benefit from these changes, it must run on the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="7d89d-110">웹 애플리케이션은 다음과 같은 방법으로 이러한 변경의 이점을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d89d-110">The web application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="7d89d-111">기본적으로 다음 AppContext 스위치를 사용하여 새로운 액세스 가능성 기능을 지원하는 Visual Studio 2017 15.3 이상을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="7d89d-111">Install Visual Studio 2017 15.3 or later, which supports the new accessibility features with the following AppContext Switch by default.</span></span>
- <span data-ttu-id="7d89d-112">다음 예제와 같이 devenv.exe.config 파일의 `<runtime>` 섹션에 `Switch.UseLegacyAccessibilityFeatures` AppContext 스위치를 추가하고 이를 `false`로 설정하여 레거시 액세스 가능성 동작을 옵트아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="7d89d-112">Opt out of the legacy accessibility behaviors by adding the `Switch.UseLegacyAccessibilityFeatures` AppContext switch to the `<runtime>` section in the devenv.exe.config file and setting it to `false`, as the following example shows.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
<runtime>
...
<!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false'  -->
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
...
</runtime>
</configuration>
```

<span data-ttu-id="7d89d-113">.NET Framework 4.7.1 이상을 대상으로 하고 레거시 액세스 가능성 동작을 유지하려는 애플리케이션은 이 AppContext 스위치를 `true`로 명확하게 설정하여 레거시 액세스 가능성 기능 사용을 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d89d-113">Applications that target the .NET Framework 4.7.1 or later and want to preserve the legacy accessibility behavior can opt in to the use of legacy accessibility features by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="7d89d-114">이름</span><span class="sxs-lookup"><span data-stu-id="7d89d-114">Name</span></span>    | <span data-ttu-id="7d89d-115">값</span><span class="sxs-lookup"><span data-stu-id="7d89d-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7d89d-116">Scope</span><span class="sxs-lookup"><span data-stu-id="7d89d-116">Scope</span></span>   | <span data-ttu-id="7d89d-117">부</span><span class="sxs-lookup"><span data-stu-id="7d89d-117">Minor</span></span>       |
| <span data-ttu-id="7d89d-118">버전</span><span class="sxs-lookup"><span data-stu-id="7d89d-118">Version</span></span> | <span data-ttu-id="7d89d-119">4.7.1</span><span class="sxs-lookup"><span data-stu-id="7d89d-119">4.7.1</span></span>       |
| <span data-ttu-id="7d89d-120">형식</span><span class="sxs-lookup"><span data-stu-id="7d89d-120">Type</span></span>    | <span data-ttu-id="7d89d-121">대상 변경</span><span class="sxs-lookup"><span data-stu-id="7d89d-121">Retargeting</span></span> |
