---
title: IMetaDataImport::EnumMembers 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type:
- apiref
ms.openlocfilehash: cc3bc5140da0634b5172f6253de3de37bff487f1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492037"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="6efe0-102">IMetaDataImport::EnumMembers 메서드</span><span class="sxs-lookup"><span data-stu-id="6efe0-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="6efe0-103">지정한 형식의 멤버를 나타내는 MemberDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="6efe0-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6efe0-104">구문</span><span class="sxs-lookup"><span data-stu-id="6efe0-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembers (
   [in, out]  HCORENUM    *phEnum,
   [in]  mdTypeDef   cl,
   [out] mdToken     rMembers[],
   [in]  ULONG       cMax,
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6efe0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6efe0-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="6efe0-106">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6efe0-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="6efe0-107">진행 멤버가 열거 될 형식을 나타내는 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="6efe0-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="6efe0-108">제한이 MemberDef 토큰을 보유 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6efe0-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6efe0-109">[in] `rMembers` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6efe0-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="6efe0-110">제한이 에서 반환 된 실제 MemberDef 토큰 수입니다 `rMembers` .</span><span class="sxs-lookup"><span data-stu-id="6efe0-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6efe0-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="6efe0-111">Return Value</span></span>  
  
|<span data-ttu-id="6efe0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6efe0-112">HRESULT</span></span>|<span data-ttu-id="6efe0-113">설명</span><span class="sxs-lookup"><span data-stu-id="6efe0-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6efe0-114">`EnumMembers`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6efe0-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6efe0-115">열거할 MemberDef 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6efe0-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="6efe0-116">이 경우는 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="6efe0-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6efe0-117">설명</span><span class="sxs-lookup"><span data-stu-id="6efe0-117">Remarks</span></span>  
 <span data-ttu-id="6efe0-118">클래스에 대 한 멤버의 컬렉션을 열거 하는 경우 `EnumMembers` 클래스에 직접 정의 된 멤버 (필드와 메서드, 속성 또는 이벤트 **아님** )만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6efe0-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span></span> <span data-ttu-id="6efe0-119">클래스가 상속 된 멤버에 대 한 구현을 제공 하는 경우에도 클래스가 상속 하는 멤버를 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6efe0-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="6efe0-120">상속 된 멤버를 열거 하려면 호출자가 상속 체인을 명시적으로 탐색 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6efe0-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="6efe0-121">상속 체인에 대 한 규칙은 원래 메타 데이터를 내보낸 언어 또는 컴파일러에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6efe0-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>

 <span data-ttu-id="6efe0-122">속성 및 이벤트는에 의해 열거 되지 않습니다 `EnumMembers` .</span><span class="sxs-lookup"><span data-stu-id="6efe0-122">Properties and events are not enumerated by `EnumMembers`.</span></span> <span data-ttu-id="6efe0-123">이를 열거 하려면 [Enumproperties](imetadataimport-enumproperties-method.md) 또는 [enumproperties](imetadataimport-enumevents-method.md)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6efe0-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="6efe0-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6efe0-124">Requirements</span></span>  
 <span data-ttu-id="6efe0-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6efe0-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6efe0-126">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="6efe0-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6efe0-127">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6efe0-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6efe0-128">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6efe0-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6efe0-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6efe0-129">See also</span></span>

- [<span data-ttu-id="6efe0-130">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6efe0-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="6efe0-131">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6efe0-131">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
