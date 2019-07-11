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
ms.openlocfilehash: 8093a702069e4ecd4dad761ad0a431abe81d6141
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780421"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="2ca0b-102">StrongNameHashSize 함수</span><span class="sxs-lookup"><span data-stu-id="2ca0b-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="2ca0b-103">지정된 해시 알고리즘을 사용하여 해시에 필요한 버퍼 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2ca0b-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="2ca0b-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ca0b-104">This function has been deprecated.</span></span> <span data-ttu-id="2ca0b-105">사용 된 [iclrstrongname:: Strongnamehashsize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ca0b-105">Use the [ICLRStrongName::StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ca0b-106">구문</span><span class="sxs-lookup"><span data-stu-id="2ca0b-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ca0b-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2ca0b-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="2ca0b-108">[in] 버퍼 크기를 계산 하는 데 사용 된 해시 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="2ca0b-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="2ca0b-109">[out] 반환 된 버퍼 크기 (바이트)에서입니다.</span><span class="sxs-lookup"><span data-stu-id="2ca0b-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ca0b-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="2ca0b-110">Return Value</span></span>  
 <span data-ttu-id="2ca0b-111">`true` 성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="2ca0b-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ca0b-112">설명</span><span class="sxs-lookup"><span data-stu-id="2ca0b-112">Remarks</span></span>  
 <span data-ttu-id="2ca0b-113">경우는 `StrongNameHashSize` 함수가 성공적으로 완료으로 호출 되지 않으면 합니다 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 마지막 생성 된 오류를 검색 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="2ca0b-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ca0b-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2ca0b-114">Requirements</span></span>  
 <span data-ttu-id="2ca0b-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2ca0b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ca0b-116">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="2ca0b-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="2ca0b-117">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2ca0b-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2ca0b-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ca0b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ca0b-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="2ca0b-119">See also</span></span>

- [<span data-ttu-id="2ca0b-120">StrongNameHashSize 메서드</span><span class="sxs-lookup"><span data-stu-id="2ca0b-120">StrongNameHashSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="2ca0b-121">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2ca0b-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
