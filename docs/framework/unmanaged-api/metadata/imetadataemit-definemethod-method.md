---
title: IMetaDataEmit::DefineMethod 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type:
- apiref
ms.openlocfilehash: d4f3c95428d6f0f8807e284c5b54582428176511
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177670"
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="73651-102">IMetaDataEmit::DefineMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="73651-102">IMetaDataEmit::DefineMethod Method</span></span>
<span data-ttu-id="73651-103">지정된 시그니처를 사용하여 메서드 또는 전역 함수에 대한 정의를 만들고 해당 메서드 정의에 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="73651-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73651-104">구문</span><span class="sxs-lookup"><span data-stu-id="73651-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethod (
    [in]  mdTypeDef         td,
    [in]  LPCWSTR           szName,
    [in]  DWORD             dwMethodFlags,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [in]  ULONG             ulCodeRVA,
    [in]  DWORD             dwImplFlags,
    [out] mdMethodDef      *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73651-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="73651-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="73651-106">【인】 메서드의 상위 클래스 또는 상위 인터페이스의 `mdTypedef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="73651-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="73651-107">전역 `td` `mdTokenNil`함수를 정의하는 경우 을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="73651-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="73651-108">【인】 유니코드의 멤버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="73651-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="73651-109">【인】 메서드 또는 전역 함수의 특성을 지정하는 [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="73651-109">[in] A value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="73651-110">【인】 메서드 시그니처입니다.</span><span class="sxs-lookup"><span data-stu-id="73651-110">[in] The method signature.</span></span> <span data-ttu-id="73651-111">서명은 제공된 대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="73651-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="73651-112">매개 변수에 대한 추가 정보를 지정해야 하는 경우 [IMetaDataEmit:SetParamProps 메서드를](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="73651-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="73651-113">【인】 의 바이트 `pvSigBlob`수입니다.</span><span class="sxs-lookup"><span data-stu-id="73651-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="73651-114">【인】 코드의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="73651-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="73651-115">【인】 메서드의 구현 기능을 지정 하는 [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="73651-115">[in] A value of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="73651-116">【아웃】 멤버 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="73651-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73651-117">설명</span><span class="sxs-lookup"><span data-stu-id="73651-117">Remarks</span></span>  
 <span data-ttu-id="73651-118">메타데이터 API는 호출자가 매개 변수에 지정된 지정된 둘러싸는 클래스 또는 인터페이스에 대해 메서드를 내보내는 것과 동일한 순서로 메서드를 `td` 유지하도록 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="73651-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="73651-119">사용 및 특정 `DefineMethod` 매개 변수 설정에 대한 추가 정보는 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73651-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="73651-120">V테이블의 슬롯</span><span class="sxs-lookup"><span data-stu-id="73651-120">Slots in the V-table</span></span>  
 <span data-ttu-id="73651-121">런타임은 메서드 정의를 사용하여 v-테이블 슬롯을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="73651-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="73651-122">COM 인터페이스 레이아웃을 사용하여 패리티를 보존하는 것과 같이 하나 이상의 슬롯을 건너뛰어야 하는 경우 더미 메서드는 v-table의 슬롯 또는 슬롯을 차지하도록 정의됩니다. `dwMethodFlags` [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) 열거형의 `mdRTSpecialName` 값으로 설정하고 이름을 다음과 같이 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="73651-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="73651-123">_VtblGap\<*시퀀스수*>\<\_*카운트오브슬롯*></span><span class="sxs-lookup"><span data-stu-id="73651-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>
  
 <span data-ttu-id="73651-124">*여기서 SequenceNumber는* 메서드의 시퀀스 번호이며 *CountOfSlots는* v 테이블에서 건너뛸 슬롯 수입니다.</span><span class="sxs-lookup"><span data-stu-id="73651-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="73651-125">*CountOfSlots를* 생략하면 1이 가정됩니다.</span><span class="sxs-lookup"><span data-stu-id="73651-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="73651-126">이러한 더미 메서드는 관리되는 코드또는 관리되지 않는 코드에서 호출할 수 없으며 관리되거나 관리되지 않는 코드에서 호출하려는 모든 시도는 예외를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="73651-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="73651-127">유일한 목적은 런타임이 COM 통합을 위해 생성하는 v-table의 공간을 차지합니다.</span><span class="sxs-lookup"><span data-stu-id="73651-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="73651-128">중복 방법</span><span class="sxs-lookup"><span data-stu-id="73651-128">Duplicate Methods</span></span>  
 <span data-ttu-id="73651-129">중복 메서드를 정의해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73651-129">You should not define duplicate methods.</span></span> <span data-ttu-id="73651-130">`DefineMethod` 즉, `td`에서 `wzName` `pvSig` 의 값 집합을 중복하여 호출해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73651-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="73651-131">(이 세 매개 변수는 함께 메서드를 고유하게 정의합니다.)</span><span class="sxs-lookup"><span data-stu-id="73651-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="73651-132">그러나 메서드 정의 중 하나에 대해 `mdPrivateScope` `dwMethodFlags` 매개 변수의 비트를 설정하는 경우 중복 트리플을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73651-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="73651-133">비트는 `mdPrivateScope` 컴파일러가 이 메서드 정의에 대한 참조를 내제공하지 않음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="73651-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="73651-134">방법 구현 정보</span><span class="sxs-lookup"><span data-stu-id="73651-134">Method Implementation Information</span></span>  
 <span data-ttu-id="73651-135">메서드 구현에 대한 정보는 메서드가 선언될 때 알려져 있지 않은 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="73651-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="73651-136">따라서 을 호출할 `ulCodeRVA` `dwImplFlags` `DefineMethod`때 및 매개 변수에 값을 전달할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73651-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="73651-137">이 값은 나중에 [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) 또는 [IMetaDataEmemit::SetRVA를](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)통해 적절히 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73651-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="73651-138">플랫폼 호출(PInvoke) 또는 COM interop 시나리오와 같은 일부 상황에서는 메서드 본문이 `ulCodeRVA` 제공되지 않으며 0으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73651-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="73651-139">이러한 상황에서는 런타임에서 구현을 찾므로 메서드에 추상태그가 지정되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73651-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="73651-140">PInvoke에 대한 방법 정의</span><span class="sxs-lookup"><span data-stu-id="73651-140">Defining a Method for PInvoke</span></span>  
 <span data-ttu-id="73651-141">PInvoke를 통해 호출되는 각 관리되지 않는 함수에 대해 대상 관리되지 않는 함수를 나타내는 관리되는 메서드를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73651-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="73651-142">관리되는 메서드를 정의하려면 PInvoke가 사용되는 방식에 따라 특정 값으로 설정된 일부 매개 변수와 함께 사용합니다. `DefineMethod`</span><span class="sxs-lookup"><span data-stu-id="73651-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
- <span data-ttu-id="73651-143">True PInvoke - 관리되지 않는 DLL에 상주하는 외부 관리되지 않는 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="73651-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
- <span data-ttu-id="73651-144">로컬 PInvoke - 현재 관리되는 모듈에 포함된 기본 관리되지 않는 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="73651-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="73651-145">매개 변수 설정은 다음 표에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="73651-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="73651-146">매개 변수</span><span class="sxs-lookup"><span data-stu-id="73651-146">Parameter</span></span>|<span data-ttu-id="73651-147">진정한 핀보크에 대한 값</span><span class="sxs-lookup"><span data-stu-id="73651-147">Values for true PInvoke</span></span>|<span data-ttu-id="73651-148">로컬 PInvoke의 값</span><span class="sxs-lookup"><span data-stu-id="73651-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="73651-149">집합; `mdStatic` `mdSynchronized` 명확하고 `mdAbstract`.</span><span class="sxs-lookup"><span data-stu-id="73651-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="73651-150">유효한 관리 되는 형식 매개 변수를 사용 하는 유효한 공통 언어 런타임 (CLR) 메서드 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="73651-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="73651-151">유효한 관리 되는 형식 매개 변수를 사용 하는 유효한 CLR 메서드 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="73651-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="73651-152">0</span><span class="sxs-lookup"><span data-stu-id="73651-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="73651-153">`miCil` 및 `miManaged`를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="73651-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="73651-154">`miNative` 및 `miUnmanaged`를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="73651-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73651-155">요구 사항</span><span class="sxs-lookup"><span data-stu-id="73651-155">Requirements</span></span>  
 <span data-ttu-id="73651-156">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73651-156">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73651-157">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="73651-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="73651-158">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="73651-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73651-159">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73651-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73651-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73651-160">See also</span></span>

- [<span data-ttu-id="73651-161">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73651-161">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="73651-162">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73651-162">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
