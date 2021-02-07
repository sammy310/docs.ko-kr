---
description: '자세한 정보: 1004-WorkflowInstanceAborted'
title: 1004 - WorkflowInstanceAborted
ms.date: 03/30/2017
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
ms.openlocfilehash: 4aaa0899da9b0b8510684a13537a8cb8f9117ee1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755621"
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="a3015-103">1004 - WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="a3015-103">1004 - WorkflowInstanceAborted</span></span>

## <a name="properties"></a><span data-ttu-id="a3015-104">속성</span><span class="sxs-lookup"><span data-stu-id="a3015-104">Properties</span></span>

|||
|-|-|
|<span data-ttu-id="a3015-105">ID</span><span class="sxs-lookup"><span data-stu-id="a3015-105">ID</span></span>|<span data-ttu-id="a3015-106">1004</span><span class="sxs-lookup"><span data-stu-id="a3015-106">1004</span></span>|
|<span data-ttu-id="a3015-107">키워드</span><span class="sxs-lookup"><span data-stu-id="a3015-107">Keywords</span></span>|<span data-ttu-id="a3015-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a3015-108">WFRuntime</span></span>|
|<span data-ttu-id="a3015-109">Level</span><span class="sxs-lookup"><span data-stu-id="a3015-109">Level</span></span>|<span data-ttu-id="a3015-110">정보</span><span class="sxs-lookup"><span data-stu-id="a3015-110">Information</span></span>|
|<span data-ttu-id="a3015-111">채널</span><span class="sxs-lookup"><span data-stu-id="a3015-111">Channel</span></span>|<span data-ttu-id="a3015-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="a3015-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|

## <a name="description"></a><span data-ttu-id="a3015-113">설명</span><span class="sxs-lookup"><span data-stu-id="a3015-113">Description</span></span>

<span data-ttu-id="a3015-114">워크플로 인스턴스가 예외와 함께 중단 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a3015-114">Indicates a workflow instance has aborted with an exception.</span></span>

## <a name="message"></a><span data-ttu-id="a3015-115">메시지</span><span class="sxs-lookup"><span data-stu-id="a3015-115">Message</span></span>

<span data-ttu-id="a3015-116">WorkflowInstance Id: '%1'이(가) 예외와 함께 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a3015-116">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>

## <a name="details"></a><span data-ttu-id="a3015-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="a3015-117">Details</span></span>

|<span data-ttu-id="a3015-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="a3015-118">Data Item Name</span></span>|<span data-ttu-id="a3015-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="a3015-119">Data Item Type</span></span>|<span data-ttu-id="a3015-120">설명</span><span class="sxs-lookup"><span data-stu-id="a3015-120">Description</span></span>|
|--------------------|--------------------|-----------------|
|<span data-ttu-id="a3015-121">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="a3015-121">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="a3015-122">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="a3015-122">The instance id for the workflow</span></span>|
|<span data-ttu-id="a3015-123">예외</span><span class="sxs-lookup"><span data-stu-id="a3015-123">Exception</span></span>|`xs:string`|<span data-ttu-id="a3015-124">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="a3015-124">The exception details for the exception</span></span>|
|<span data-ttu-id="a3015-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a3015-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a3015-126">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a3015-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
