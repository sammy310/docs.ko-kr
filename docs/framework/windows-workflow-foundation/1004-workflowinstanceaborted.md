---
title: 1004 - WorkflowInstanceAborted
ms.date: 03/30/2017
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
ms.openlocfilehash: d34f6f1ab6af8e06a0f28fb043faf9fe16a8b211
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008618"
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="3b546-102">1004 - WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="3b546-102">1004 - WorkflowInstanceAborted</span></span>

## <a name="properties"></a><span data-ttu-id="3b546-103">속성</span><span class="sxs-lookup"><span data-stu-id="3b546-103">Properties</span></span>

|||
|-|-|
|<span data-ttu-id="3b546-104">ID</span><span class="sxs-lookup"><span data-stu-id="3b546-104">ID</span></span>|<span data-ttu-id="3b546-105">1004</span><span class="sxs-lookup"><span data-stu-id="3b546-105">1004</span></span>|
|<span data-ttu-id="3b546-106">키워드</span><span class="sxs-lookup"><span data-stu-id="3b546-106">Keywords</span></span>|<span data-ttu-id="3b546-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3b546-107">WFRuntime</span></span>|
|<span data-ttu-id="3b546-108">수준</span><span class="sxs-lookup"><span data-stu-id="3b546-108">Level</span></span>|<span data-ttu-id="3b546-109">정보</span><span class="sxs-lookup"><span data-stu-id="3b546-109">Information</span></span>|
|<span data-ttu-id="3b546-110">채널</span><span class="sxs-lookup"><span data-stu-id="3b546-110">Channel</span></span>|<span data-ttu-id="3b546-111">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="3b546-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|

## <a name="description"></a><span data-ttu-id="3b546-112">설명</span><span class="sxs-lookup"><span data-stu-id="3b546-112">Description</span></span>

<span data-ttu-id="3b546-113">워크플로 인스턴스가 예외와 함께 중단 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3b546-113">Indicates a workflow instance has aborted with an exception.</span></span>

## <a name="message"></a><span data-ttu-id="3b546-114">메시지</span><span class="sxs-lookup"><span data-stu-id="3b546-114">Message</span></span>

<span data-ttu-id="3b546-115">WorkflowInstance Id: '%1'이(가) 예외와 함께 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3b546-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>

## <a name="details"></a><span data-ttu-id="3b546-116">설명</span><span class="sxs-lookup"><span data-stu-id="3b546-116">Details</span></span>

|<span data-ttu-id="3b546-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="3b546-117">Data Item Name</span></span>|<span data-ttu-id="3b546-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="3b546-118">Data Item Type</span></span>|<span data-ttu-id="3b546-119">설명</span><span class="sxs-lookup"><span data-stu-id="3b546-119">Description</span></span>|
|--------------------|--------------------|-----------------|
|<span data-ttu-id="3b546-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="3b546-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="3b546-121">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="3b546-121">The instance id for the workflow</span></span>|
|<span data-ttu-id="3b546-122">예외</span><span class="sxs-lookup"><span data-stu-id="3b546-122">Exception</span></span>|`xs:string`|<span data-ttu-id="3b546-123">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="3b546-123">The exception details for the exception</span></span>|
|<span data-ttu-id="3b546-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3b546-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="3b546-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3b546-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
