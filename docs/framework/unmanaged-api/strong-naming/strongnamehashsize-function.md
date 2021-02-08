---
description: '자세히 알아보기: StrongNameHashSize 함수'
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
ms.openlocfilehash: 3e6700bfce3ba480814f3837011c5f8f7107bbd5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781248"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="10062-103">StrongNameHashSize 함수</span><span class="sxs-lookup"><span data-stu-id="10062-103">StrongNameHashSize Function</span></span>

<span data-ttu-id="10062-104">지정된 해시 알고리즘을 사용하여 해시에 필요한 버퍼 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="10062-104">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="10062-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10062-105">This function has been deprecated.</span></span> <span data-ttu-id="10062-106">대신 [ICLRStrongName:: StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="10062-106">Use the [ICLRStrongName::StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10062-107">구문</span><span class="sxs-lookup"><span data-stu-id="10062-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10062-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="10062-108">Parameters</span></span>  

 `ulHashAlg`  
 <span data-ttu-id="10062-109">진행 버퍼 크기를 계산 하는 데 사용 되는 해시 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="10062-109">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="10062-110">제한이 반환 된 버퍼 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="10062-110">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10062-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="10062-111">Return Value</span></span>  

 <span data-ttu-id="10062-112">`true` 성공적으로 완료 되 면 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="10062-112">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10062-113">설명</span><span class="sxs-lookup"><span data-stu-id="10062-113">Remarks</span></span>  

 <span data-ttu-id="10062-114">`StrongNameHashSize`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="10062-114">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10062-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="10062-115">Requirements</span></span>  

 <span data-ttu-id="10062-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10062-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10062-117">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="10062-117">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="10062-118">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10062-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="10062-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10062-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10062-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="10062-120">See also</span></span>

- [<span data-ttu-id="10062-121">StrongNameHashSize 메서드</span><span class="sxs-lookup"><span data-stu-id="10062-121">StrongNameHashSize Method</span></span>](../hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="10062-122">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10062-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
