---
description: '자세히 알아보기: ICLRRuntimeInfo:: GetInterface 메서드'
title: ICLRRuntimeInfo::GetInterface 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetInterface
helpviewer_keywords:
- GetInterface method [.NET Framework hosting]
- ICLRRuntimeInfo::GetInterface method [.NET Framework hosting]
ms.assetid: cc7b0e5b-48c3-4509-8ebb-611ddb1f7ec2
topic_type:
- apiref
ms.openlocfilehash: 5a5c55823ff9954735a712423d8aaab1256c947d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637133"
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="b736c-103">ICLRRuntimeInfo::GetInterface 메서드</span><span class="sxs-lookup"><span data-stu-id="b736c-103">ICLRRuntimeInfo::GetInterface Method</span></span>

<span data-ttu-id="b736c-104">CLR을 현재 프로세스로 로드 하 고 [ICLRRuntimeHost](iclrruntimehost-interface.md), [ICLRStrongName](iclrstrongname-interface.md)및 [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md)와 같은 런타임 인터페이스 포인터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b736c-104">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](iclrruntimehost-interface.md), [ICLRStrongName](iclrstrongname-interface.md), and [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="b736c-105">이 메서드는 `CorBindTo` [사용 되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md) 섹션의 모든 \* 함수를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="b736c-105">This method supersedes all the `CorBindTo`\* functions in the [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b736c-106">구문</span><span class="sxs-lookup"><span data-stu-id="b736c-106">Syntax</span></span>  
  
```cpp  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b736c-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b736c-107">Parameters</span></span>  

 `rclsid`  
 <span data-ttu-id="b736c-108">진행 Coclass의 CLSID 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b736c-108">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="b736c-109">진행 요청 된 인터페이스의 IID입니다 `rclsid` .</span><span class="sxs-lookup"><span data-stu-id="b736c-109">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="b736c-110">제한이 쿼리 된 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b736c-110">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b736c-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="b736c-111">Return Value</span></span>  

 <span data-ttu-id="b736c-112">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b736c-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b736c-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b736c-113">HRESULT</span></span>|<span data-ttu-id="b736c-114">설명</span><span class="sxs-lookup"><span data-stu-id="b736c-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b736c-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="b736c-115">S_OK</span></span>|<span data-ttu-id="b736c-116">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b736c-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="b736c-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="b736c-117">E_POINTER</span></span>|<span data-ttu-id="b736c-118">`ppUnk`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="b736c-118">`ppUnk` is null.</span></span>|  
|<span data-ttu-id="b736c-119">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b736c-119">E_OUTOFMEMORY</span></span>|<span data-ttu-id="b736c-120">메모리가 부족 하 여 요청을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b736c-120">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="b736c-121">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="b736c-121">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="b736c-122">다른 런타임이 이미 레거시 CLR 버전 2 활성화 정책에 바인딩되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b736c-122">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b736c-123">설명</span><span class="sxs-lookup"><span data-stu-id="b736c-123">Remarks</span></span>  

 <span data-ttu-id="b736c-124">이 메서드로 인해 CLR이 로드 되지만 초기화 되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b736c-124">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="b736c-125">다음 표에서는 및에 대해 지원 되는 조합을 보여 줍니다 `rclsid` `riid` .</span><span class="sxs-lookup"><span data-stu-id="b736c-125">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="b736c-126">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="b736c-126">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="b736c-127">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="b736c-127">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="b736c-128">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="b736c-128">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="b736c-129">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="b736c-129">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="b736c-130">CLSID_CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b736c-130">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="b736c-131">IID_ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b736c-131">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="b736c-132">CLSID_CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b736c-132">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="b736c-133">IID_ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b736c-133">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="b736c-134">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="b736c-134">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="b736c-135">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="b736c-135">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="b736c-136">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="b736c-136">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="b736c-137">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="b736c-137">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="b736c-138">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="b736c-138">CLSID_CLRStrongName</span></span>|<span data-ttu-id="b736c-139">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="b736c-139">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b736c-140">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b736c-140">Requirements</span></span>  

 <span data-ttu-id="b736c-141">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b736c-141">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b736c-142">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="b736c-142">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b736c-143">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b736c-143">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b736c-144">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b736c-144">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b736c-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b736c-145">See also</span></span>

- [<span data-ttu-id="b736c-146">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b736c-146">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="b736c-147">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b736c-147">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="b736c-148">호스팅</span><span class="sxs-lookup"><span data-stu-id="b736c-148">Hosting</span></span>](index.md)
