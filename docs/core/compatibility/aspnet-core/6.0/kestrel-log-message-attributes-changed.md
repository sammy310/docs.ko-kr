---
title: '호환성이 손상되는 변경: Kestrel: 로그 메시지 특성이 변경됨'
description: 'ASP.NET Core 6.0의 호환성이 손상되는 변경에 대해 알아보기. Kestrel: 로그 메시지 특성이 변경됨'
author: scottaddie
ms.author: scaddie
ms.date: 02/01/2021
ms.openlocfilehash: 30b03c22a6c85623fec7db14b58b169f887395a0
ms.sourcegitcommit: 4df8e005c074ceb1f978f007b222fe253be2baf3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2021
ms.locfileid: "99551535"
---
# <a name="kestrel-log-message-attributes-changed"></a><span data-ttu-id="277ae-103">Kestrel: 로그 메시지 특성이 변경됨</span><span class="sxs-lookup"><span data-stu-id="277ae-103">Kestrel: Log message attributes changed</span></span>

<span data-ttu-id="277ae-104">Kestrel 로그 메시지에는 ID 및 이름이 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="277ae-104">Kestrel log messages have associated IDs and names.</span></span> <span data-ttu-id="277ae-105">이러한 특성은 다양한 종류의 로그 메시지를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="277ae-105">These attributes uniquely identify different kinds of log messages.</span></span> <span data-ttu-id="277ae-106">이러한 ID 및 이름 중 일부가 잘못 중복되었습니다.</span><span class="sxs-lookup"><span data-stu-id="277ae-106">Some of those IDs and names were incorrectly duplicated.</span></span> <span data-ttu-id="277ae-107">이 중복 문제가 ASP.NET Core 6.0에서 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="277ae-107">This duplication problem is fixed in ASP.NET Core 6.0.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="277ae-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="277ae-108">Version introduced</span></span>

<span data-ttu-id="277ae-109">6.0</span><span class="sxs-lookup"><span data-stu-id="277ae-109">6.0</span></span>

## <a name="old-behavior"></a><span data-ttu-id="277ae-110">이전 동작</span><span class="sxs-lookup"><span data-stu-id="277ae-110">Old behavior</span></span>

<span data-ttu-id="277ae-111">다음 표에서는 ASP.NET Core 6.0 이전에서 영향을 받는 로그 메시지의 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="277ae-111">The following table shows the state of the affected log messages before ASP.NET Core 6.0.</span></span>

| <span data-ttu-id="277ae-112">메시지 설명</span><span class="sxs-lookup"><span data-stu-id="277ae-112">Message description</span></span>                   | <span data-ttu-id="277ae-113">속성</span><span class="sxs-lookup"><span data-stu-id="277ae-113">Name</span></span>                    | <span data-ttu-id="277ae-114">ID</span><span class="sxs-lookup"><span data-stu-id="277ae-114">ID</span></span> |
|---------------------------------------|-------------------------|----|
| <span data-ttu-id="277ae-115">HTTP/2 연결 닫힘 로그 메시지</span><span class="sxs-lookup"><span data-stu-id="277ae-115">HTTP/2 connection closed log messages</span></span> | `Http2ConnectionClosed` | <span data-ttu-id="277ae-116">36</span><span class="sxs-lookup"><span data-stu-id="277ae-116">36</span></span> |
| <span data-ttu-id="277ae-117">HTTP/2 프레임 전송 로그 메시지</span><span class="sxs-lookup"><span data-stu-id="277ae-117">HTTP/2 frame sending log messages</span></span>     | `Http2FrameReceived`    | <span data-ttu-id="277ae-118">37</span><span class="sxs-lookup"><span data-stu-id="277ae-118">37</span></span> |

## <a name="new-behavior"></a><span data-ttu-id="277ae-119">새 동작</span><span class="sxs-lookup"><span data-stu-id="277ae-119">New behavior</span></span>

<span data-ttu-id="277ae-120">다음 표에서는 ASP.NET Core 6.0에서 영향을 받는 로그 메시지의 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="277ae-120">The following table shows the state of the affected log messages in ASP.NET Core 6.0.</span></span>

| <span data-ttu-id="277ae-121">메시지 설명</span><span class="sxs-lookup"><span data-stu-id="277ae-121">Message description</span></span>                   | <span data-ttu-id="277ae-122">속성</span><span class="sxs-lookup"><span data-stu-id="277ae-122">Name</span></span>                    | <span data-ttu-id="277ae-123">ID</span><span class="sxs-lookup"><span data-stu-id="277ae-123">ID</span></span> |
|---------------------------------------|-------------------------|----|
| <span data-ttu-id="277ae-124">HTTP/2 연결 닫힘 로그 메시지</span><span class="sxs-lookup"><span data-stu-id="277ae-124">HTTP/2 connection closed log messages</span></span> | `Http2ConnectionClosed` | <span data-ttu-id="277ae-125">48</span><span class="sxs-lookup"><span data-stu-id="277ae-125">48</span></span> |
| <span data-ttu-id="277ae-126">HTTP/2 프레임 전송 로그 메시지</span><span class="sxs-lookup"><span data-stu-id="277ae-126">HTTP/2 frame sending log messages</span></span>     | `Http2FrameSending`     | <span data-ttu-id="277ae-127">49</span><span class="sxs-lookup"><span data-stu-id="277ae-127">49</span></span> |

## <a name="reason-for-change"></a><span data-ttu-id="277ae-128">변경 이유</span><span class="sxs-lookup"><span data-stu-id="277ae-128">Reason for change</span></span>

<span data-ttu-id="277ae-129">로그 ID 및 이름은 서로 다른 메시지 유형을 식별할 수 있도록 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="277ae-129">Log IDs and names should be unique so different message types can be identified.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="277ae-130">권장 조치</span><span class="sxs-lookup"><span data-stu-id="277ae-130">Recommended action</span></span>

<span data-ttu-id="277ae-131">이전 ID 및 이름을 참조하는 코드 또는 구성이 있는 경우 새 ID 및 이름을 사용하도록 해당 참조를 업데이트하세요.</span><span class="sxs-lookup"><span data-stu-id="277ae-131">If you have code or configuration that references the old IDs and names, update those references to use the new IDs and names.</span></span>

<!--

## Category

ASP.NET Core

## Affected APIs

Not detectable via API analysis

-->
