---
description: '자세히 알아보기: IMetaDataEmit2 인터페이스'
title: IMetaDataEmit2 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2
helpviewer_keywords:
- IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type:
- apiref
ms.openlocfilehash: db1880d64bf3b1e9084d6745251c174788a4afe7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745686"
---
# <a name="imetadataemit2-interface"></a><span data-ttu-id="8fb7d-103">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8fb7d-103">IMetaDataEmit2 Interface</span></span>

<span data-ttu-id="8fb7d-104">[IMetaDataEmit](imetadataemit-interface.md) 인터페이스를 주로 확장 하 여 제네릭 형식으로 작업 하는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-104">Extends the [IMetaDataEmit](imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8fb7d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8fb7d-105">Methods</span></span>  
  
|<span data-ttu-id="8fb7d-106">메서드</span><span class="sxs-lookup"><span data-stu-id="8fb7d-106">Method</span></span>|<span data-ttu-id="8fb7d-107">설명</span><span class="sxs-lookup"><span data-stu-id="8fb7d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8fb7d-108">DefineGenericParam 메서드</span><span class="sxs-lookup"><span data-stu-id="8fb7d-108">DefineGenericParam Method</span></span>](imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="8fb7d-109">제네릭 형식 매개 변수에 대 한 정의를 만들고 해당 제네릭 형식 매개 변수에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-109">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="8fb7d-110">DefineMethodSpec 메서드</span><span class="sxs-lookup"><span data-stu-id="8fb7d-110">DefineMethodSpec Method</span></span>](imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="8fb7d-111">메서드의 제네릭 인스턴스를 만들고 해당 정의에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-111">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="8fb7d-112">GetDeltaSaveSize 메서드</span><span class="sxs-lookup"><span data-stu-id="8fb7d-112">GetDeltaSaveSize Method</span></span>](imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="8fb7d-113">현재 편집 하며 계속 하기 세션의 변경 내용을 표현 하는 데 필요한 데이터 크기의 차이를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-113">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="8fb7d-114">ResetENCLog 메서드</span><span class="sxs-lookup"><span data-stu-id="8fb7d-114">ResetENCLog Method</span></span>](imetadataemit2-resetenclog-method.md)|<span data-ttu-id="8fb7d-115">편집 하며 계속 하기 로그를 다시 설정 하 고 새 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-115">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="8fb7d-116">SaveDelta 메서드</span><span class="sxs-lookup"><span data-stu-id="8fb7d-116">SaveDelta Method</span></span>](imetadataemit2-savedelta-method.md)|<span data-ttu-id="8fb7d-117">현재 편집 하며 계속 하기 세션의 변경 내용을 지정 된 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-117">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="8fb7d-118">SaveDeltaToMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="8fb7d-118">SaveDeltaToMemory Method</span></span>](imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="8fb7d-119">현재 편집 하며 계속 하기 세션의 변경 내용을 메모리로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-119">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="8fb7d-120">SaveDeltaToStream 메서드</span><span class="sxs-lookup"><span data-stu-id="8fb7d-120">SaveDeltaToStream Method</span></span>](imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="8fb7d-121">현재 편집 하며 계속 하기 세션의 변경 내용을 지정 된 스트림에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-121">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="8fb7d-122">SetGenericParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="8fb7d-122">SetGenericParamProps Method</span></span>](imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="8fb7d-123">지정 된 토큰이 참조 하는 제네릭 매개 변수 정의에 대 한 속성 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-123">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8fb7d-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8fb7d-124">Requirements</span></span>  

 <span data-ttu-id="8fb7d-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fb7d-126">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="8fb7d-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8fb7d-127">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-127">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8fb7d-128">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fb7d-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fb7d-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8fb7d-129">See also</span></span>

- [<span data-ttu-id="8fb7d-130">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8fb7d-130">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="8fb7d-131">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8fb7d-131">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
