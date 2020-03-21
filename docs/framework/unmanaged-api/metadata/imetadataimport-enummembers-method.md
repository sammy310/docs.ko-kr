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
ms.openlocfilehash: 20c7a90f27defa18a5ef311d1f3a549b81fc5c40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175488"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="02206-102">IMetaDataImport::EnumMembers 메서드</span><span class="sxs-lookup"><span data-stu-id="02206-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="02206-103">지정한 형식의 멤버를 나타내는 MemberDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="02206-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02206-104">구문</span><span class="sxs-lookup"><span data-stu-id="02206-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembers (
   [in, out]  HCORENUM    *phEnum,
   [in]  mdTypeDef   cl,
   [out] mdToken     rMembers[],
   [in]  ULONG       cMax,
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02206-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="02206-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="02206-106">【인, 아웃】 열거형에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="02206-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="02206-107">【인】 멤버를 등록할 형식을 나타내는 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="02206-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="02206-108">【아웃】 MemberDef 토큰을 보유하는 데 사용되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="02206-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="02206-109">[in] `rMembers` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="02206-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="02206-110">【아웃】 에서 반환된 멤버Def 토큰의 `rMembers`실제 수입니다.</span><span class="sxs-lookup"><span data-stu-id="02206-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02206-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="02206-111">Return Value</span></span>  
  
|<span data-ttu-id="02206-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="02206-112">HRESULT</span></span>|<span data-ttu-id="02206-113">Description</span><span class="sxs-lookup"><span data-stu-id="02206-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="02206-114">`EnumMembers`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="02206-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="02206-115">등록할 MemberDef 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02206-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="02206-116">이 경우 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="02206-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02206-117">설명</span><span class="sxs-lookup"><span data-stu-id="02206-117">Remarks</span></span>  
 <span data-ttu-id="02206-118">클래스에 대한 멤버 컬렉션을 등록할 때 `EnumMembers` 클래스에 직접 정의된 멤버(필드 및 메서드는 있지만 속성이나 이벤트는 **아님)만** 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="02206-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span></span> <span data-ttu-id="02206-119">클래스가 상속된 멤버에 대한 구현을 제공하는 경우에도 클래스가 상속하는 멤버는 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02206-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="02206-120">상속된 멤버를 등록하려면 호출자는 상속 체인을 명시적으로 걸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02206-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="02206-121">상속 체인에 대한 규칙은 원래 메타데이터를 내보낸 언어 또는 컴파일러에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02206-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>

 <span data-ttu-id="02206-122">속성 및 이벤트는 에 의해 `EnumMembers`지어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02206-122">Properties and events are not enumerated by `EnumMembers`.</span></span> <span data-ttu-id="02206-123">열거형으로 열거하려면 [EnumProperties](imetadataimport-enumproperties-method.md) 또는 [EnumEvents를](imetadataimport-enumevents-method.md)사용합니다.</span><span class="sxs-lookup"><span data-stu-id="02206-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="02206-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02206-124">Requirements</span></span>  
 <span data-ttu-id="02206-125">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02206-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02206-126">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="02206-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="02206-127">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="02206-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="02206-128">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02206-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02206-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02206-129">See also</span></span>

- [<span data-ttu-id="02206-130">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02206-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="02206-131">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02206-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
