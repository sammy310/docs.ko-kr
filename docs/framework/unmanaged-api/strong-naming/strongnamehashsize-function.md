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
ms.openlocfilehash: 53384a5aa7f8d11f868057f892f7b60aac2e9f02
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799033"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="5690f-102">StrongNameHashSize 함수</span><span class="sxs-lookup"><span data-stu-id="5690f-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="5690f-103">지정된 해시 알고리즘을 사용하여 해시에 필요한 버퍼 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5690f-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="5690f-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5690f-104">This function has been deprecated.</span></span> <span data-ttu-id="5690f-105">대신 [ICLRStrongName:: StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5690f-105">Use the [ICLRStrongName::StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5690f-106">구문</span><span class="sxs-lookup"><span data-stu-id="5690f-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5690f-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5690f-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="5690f-108">진행 버퍼 크기를 계산 하는 데 사용 되는 해시 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="5690f-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="5690f-109">제한이 반환 된 버퍼 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="5690f-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5690f-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="5690f-110">Return Value</span></span>  
 <span data-ttu-id="5690f-111">`true`성공적으로 완료 되 면 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="5690f-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5690f-112">설명</span><span class="sxs-lookup"><span data-stu-id="5690f-112">Remarks</span></span>  
 <span data-ttu-id="5690f-113">`StrongNameHashSize` 함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="5690f-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5690f-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5690f-114">Requirements</span></span>  
 <span data-ttu-id="5690f-115">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5690f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5690f-116">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="5690f-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="5690f-117">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5690f-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5690f-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5690f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5690f-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="5690f-119">See also</span></span>

- [<span data-ttu-id="5690f-120">StrongNameHashSize 메서드</span><span class="sxs-lookup"><span data-stu-id="5690f-120">StrongNameHashSize Method</span></span>](../hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="5690f-121">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5690f-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
