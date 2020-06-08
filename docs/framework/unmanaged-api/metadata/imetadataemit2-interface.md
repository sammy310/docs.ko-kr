---
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
ms.openlocfilehash: 5a232f30da8812c6f3bd94647d74151312a8593b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493043"
---
# <a name="imetadataemit2-interface"></a><span data-ttu-id="7fb20-102">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7fb20-102">IMetaDataEmit2 Interface</span></span>
<span data-ttu-id="7fb20-103">[IMetaDataEmit](imetadataemit-interface.md) 인터페이스를 주로 확장 하 여 제네릭 형식으로 작업 하는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb20-103">Extends the [IMetaDataEmit](imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7fb20-104">메서드</span><span class="sxs-lookup"><span data-stu-id="7fb20-104">Methods</span></span>  
  
|<span data-ttu-id="7fb20-105">방법</span><span class="sxs-lookup"><span data-stu-id="7fb20-105">Method</span></span>|<span data-ttu-id="7fb20-106">설명</span><span class="sxs-lookup"><span data-stu-id="7fb20-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7fb20-107">DefineGenericParam 메서드</span><span class="sxs-lookup"><span data-stu-id="7fb20-107">DefineGenericParam Method</span></span>](imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="7fb20-108">제네릭 형식 매개 변수에 대 한 정의를 만들고 해당 제네릭 형식 매개 변수에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7fb20-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="7fb20-109">DefineMethodSpec 메서드</span><span class="sxs-lookup"><span data-stu-id="7fb20-109">DefineMethodSpec Method</span></span>](imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="7fb20-110">메서드의 제네릭 인스턴스를 만들고 해당 정의에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7fb20-110">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="7fb20-111">GetDeltaSaveSize 메서드</span><span class="sxs-lookup"><span data-stu-id="7fb20-111">GetDeltaSaveSize Method</span></span>](imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="7fb20-112">현재 편집 하며 계속 하기 세션의 변경 내용을 표현 하는 데 필요한 데이터 크기의 차이를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7fb20-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="7fb20-113">ResetENCLog 메서드</span><span class="sxs-lookup"><span data-stu-id="7fb20-113">ResetENCLog Method</span></span>](imetadataemit2-resetenclog-method.md)|<span data-ttu-id="7fb20-114">편집 하며 계속 하기 로그를 다시 설정 하 고 새 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb20-114">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="7fb20-115">SaveDelta 메서드</span><span class="sxs-lookup"><span data-stu-id="7fb20-115">SaveDelta Method</span></span>](imetadataemit2-savedelta-method.md)|<span data-ttu-id="7fb20-116">현재 편집 하며 계속 하기 세션의 변경 내용을 지정 된 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb20-116">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="7fb20-117">SaveDeltaToMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="7fb20-117">SaveDeltaToMemory Method</span></span>](imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="7fb20-118">현재 편집 하며 계속 하기 세션의 변경 내용을 메모리로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb20-118">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="7fb20-119">SaveDeltaToStream 메서드</span><span class="sxs-lookup"><span data-stu-id="7fb20-119">SaveDeltaToStream Method</span></span>](imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="7fb20-120">현재 편집 하며 계속 하기 세션의 변경 내용을 지정 된 스트림에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb20-120">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="7fb20-121">SetGenericParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="7fb20-121">SetGenericParamProps Method</span></span>](imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="7fb20-122">지정 된 토큰이 참조 하는 제네릭 매개 변수 정의에 대 한 속성 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb20-122">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7fb20-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7fb20-123">Requirements</span></span>  
 <span data-ttu-id="7fb20-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7fb20-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fb20-125">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="7fb20-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7fb20-126">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fb20-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7fb20-127">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fb20-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fb20-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7fb20-128">See also</span></span>

- [<span data-ttu-id="7fb20-129">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7fb20-129">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="7fb20-130">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7fb20-130">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
