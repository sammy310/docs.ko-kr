---
title: StrongNameGetBlobFromImage 함수
ms.date: 03/30/2017
api_name:
- StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage function [.NET Framework strong naming]
ms.assetid: 1de658e6-da32-4d01-9097-6f43c92222e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c9f53c1d0c06498c6c9cede938d115f38a47569
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478793"
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="98733-102">StrongNameGetBlobFromImage 함수</span><span class="sxs-lookup"><span data-stu-id="98733-102">StrongNameGetBlobFromImage Function</span></span>
<span data-ttu-id="98733-103">지정된 메모리 주소에 있는 어셈블리 이미지의 이진 표현을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="98733-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="98733-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98733-104">This function has been deprecated.</span></span> <span data-ttu-id="98733-105">사용 된 [iclrstrongname:: Strongnamegetblobfromimage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="98733-105">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98733-106">구문</span><span class="sxs-lookup"><span data-stu-id="98733-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98733-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="98733-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="98733-108">[in] 매핑된 어셈블리 매니페스트에 대 한 메모리 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="98733-108">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="98733-109">[in] 크기 (바이트)의 이미지 `pbBase`합니다.</span><span class="sxs-lookup"><span data-stu-id="98733-109">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="98733-110">[in] 이미지의 이진 표현을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="98733-110">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="98733-111">[out에서] 최대 크기 (바이트), 요청한 `pbBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="98733-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="98733-112">실제 크기를 바이트 단위로 반환 될 때의 `pbBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="98733-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98733-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="98733-113">Return Value</span></span>  
 <span data-ttu-id="98733-114">`true` 성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="98733-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98733-115">설명</span><span class="sxs-lookup"><span data-stu-id="98733-115">Remarks</span></span>  
 <span data-ttu-id="98733-116">경우는 `StrongNameGetBlobFromImage` 함수가 성공적으로 완료으로 호출 되지 않으면 합니다 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 마지막 생성 된 오류를 검색 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="98733-116">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98733-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="98733-117">Requirements</span></span>  
 <span data-ttu-id="98733-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="98733-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98733-119">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="98733-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="98733-120">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="98733-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="98733-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98733-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98733-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="98733-122">See also</span></span>
- [<span data-ttu-id="98733-123">StrongNameGetBlobFromImage 메서드</span><span class="sxs-lookup"><span data-stu-id="98733-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="98733-124">StrongNameGetBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="98733-124">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="98733-125">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98733-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
