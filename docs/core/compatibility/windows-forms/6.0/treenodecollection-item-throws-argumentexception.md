---
title: '호환성이 손상되는 변경: TreeNodeCollection.Item(Int32)이 사용 중인 노드에 대해 ArgumentException을 throw합니다.'
description: 할당하는 노드가 이미 TreeView에 할당되어 있는 경우 이제 TreeNodeCollection.Item(Int32)에서 ArgumentException을 throw하는 .NET 6의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 01/19/2021
ms.openlocfilehash: 29727da2e4bc3d6ac89ed88819bf03d058603f77
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255696"
---
# <a name="treenodecollectionitem-throws-exception-if-node-is-assigned-elsewhere"></a><span data-ttu-id="45660-103">노드가 다른 곳에 할당될 경우 TreeNodeCollection.Item이 예외를 throw함</span><span class="sxs-lookup"><span data-stu-id="45660-103">TreeNodeCollection.Item throws exception if node is assigned elsewhere</span></span>

<span data-ttu-id="45660-104">할당하는 노드가 이미 다른 <xref:System.Windows.Forms.TreeView>에 바인딩되어 있거나 다른 인덱스에서 이 <xref:System.Windows.Forms.TreeView>에 바인딩되어 있는 경우 <xref:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)?displayProperty=nameWithType>이 <xref:System.ArgumentException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="45660-104"><xref:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)?displayProperty=nameWithType> throws an <xref:System.ArgumentException> if the node being assigned is already bound to another <xref:System.Windows.Forms.TreeView> or to this <xref:System.Windows.Forms.TreeView> at a different index.</span></span>

## <a name="change-description"></a><span data-ttu-id="45660-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="45660-105">Change description</span></span>

<span data-ttu-id="45660-106">이전 .NET 버전에서는 이미 <xref:System.Windows.Forms.TreeView>에 바인딩되어 있는 트리 노드도 컬렉션에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45660-106">In previous .NET versions, you can assign a tree node to a collection even if it's already bound to a <xref:System.Windows.Forms.TreeView>.</span></span> <span data-ttu-id="45660-107">이로 인해 중복 노드가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45660-107">This can lead to duplicated nodes.</span></span> <span data-ttu-id="45660-108">.NET 6부터 할당하는 노드가 이미 다른 <xref:System.Windows.Forms.TreeView>에 바인딩되어 있거나 다른 인덱스에서 이 <xref:System.Windows.Forms.TreeView>에 바인딩되어 있는 경우 <xref:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)?displayProperty=nameWithType>이 <xref:System.ArgumentException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="45660-108">Starting in .NET 6, <xref:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)?displayProperty=nameWithType> throws an <xref:System.ArgumentException> if the node being assigned is already bound to another <xref:System.Windows.Forms.TreeView> or to this <xref:System.Windows.Forms.TreeView> at a different index.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="45660-109">변경 이유</span><span class="sxs-lookup"><span data-stu-id="45660-109">Reason for change</span></span>

<span data-ttu-id="45660-110">입력 매개 변수에 대한 유효성 검사가 다른 `TreeNodeCollection` API의 동작과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="45660-110">Validating the input parameter is consistent with the behavior of other `TreeNodeCollection` APIs.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="45660-111">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="45660-111">Version introduced</span></span>

<span data-ttu-id="45660-112">.NET 6 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="45660-112">.NET 6 Preview 1</span></span>

## <a name="recommended-action"></a><span data-ttu-id="45660-113">권장 조치</span><span class="sxs-lookup"><span data-stu-id="45660-113">Recommended action</span></span>

<span data-ttu-id="45660-114">컬렉션에 할당하기 전에 `TreeNode` 바인딩을 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45660-114">Make sure to unbind a `TreeNode` before assigning it to the collection.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="45660-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="45660-115">Affected APIs</span></span>

<xref:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)`

### Category

Windows Forms

-->
