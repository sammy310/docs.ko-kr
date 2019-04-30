---
title: StrongNameHashSize 함수
ms.date: 03/30/2017
api_name:
- StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameHashSize
helpviewer_keywords:
- StrongNameHashSize function [.NET Framework strong naming]
ms.assetid: 738c98d7-a60c-45fe-a296-220af05e6991
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c7e807b502e0905f9ae785203289447c71d25e04
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041025"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="dc89c-102">StrongNameHashSize 함수</span><span class="sxs-lookup"><span data-stu-id="dc89c-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="dc89c-103">지정된 해시 알고리즘을 사용하여 해시에 필요한 버퍼 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dc89c-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="dc89c-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc89c-104">This function has been deprecated.</span></span> <span data-ttu-id="dc89c-105">사용 된 [iclrstrongname:: Strongnamehashsize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc89c-105">Use the [ICLRStrongName::StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc89c-106">구문</span><span class="sxs-lookup"><span data-stu-id="dc89c-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc89c-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dc89c-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="dc89c-108">[in] 버퍼 크기를 계산 하는 데 사용 된 해시 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="dc89c-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="dc89c-109">[out] 반환 된 버퍼 크기 (바이트)에서입니다.</span><span class="sxs-lookup"><span data-stu-id="dc89c-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc89c-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="dc89c-110">Return Value</span></span>  
 <span data-ttu-id="dc89c-111">`true` 성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="dc89c-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc89c-112">설명</span><span class="sxs-lookup"><span data-stu-id="dc89c-112">Remarks</span></span>  
 <span data-ttu-id="dc89c-113">경우는 `StrongNameHashSize` 함수가 성공적으로 완료으로 호출 되지 않으면 합니다 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 마지막 생성 된 오류를 검색 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="dc89c-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc89c-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dc89c-114">Requirements</span></span>  
 <span data-ttu-id="dc89c-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc89c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc89c-116">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="dc89c-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="dc89c-117">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="dc89c-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dc89c-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc89c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc89c-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="dc89c-119">See also</span></span>

- [<span data-ttu-id="dc89c-120">StrongNameHashSize 메서드</span><span class="sxs-lookup"><span data-stu-id="dc89c-120">StrongNameHashSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="dc89c-121">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dc89c-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
