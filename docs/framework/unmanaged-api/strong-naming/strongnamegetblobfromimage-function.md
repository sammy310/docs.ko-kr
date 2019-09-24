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
ms.openlocfilehash: 86b99b29a85f498a6bfa0363a446bf589876bff9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799093"
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="5f5d6-102">StrongNameGetBlobFromImage 함수</span><span class="sxs-lookup"><span data-stu-id="5f5d6-102">StrongNameGetBlobFromImage Function</span></span>
<span data-ttu-id="5f5d6-103">지정된 메모리 주소에 있는 어셈블리 이미지의 이진 표현을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5f5d6-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="5f5d6-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5d6-104">This function has been deprecated.</span></span> <span data-ttu-id="5f5d6-105">대신 [ICLRStrongName:: StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f5d6-105">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f5d6-106">구문</span><span class="sxs-lookup"><span data-stu-id="5f5d6-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f5d6-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5f5d6-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="5f5d6-108">진행 매핑된 어셈블리 매니페스트의 메모리 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="5f5d6-108">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="5f5d6-109">진행 에 `pbBase`있는 이미지의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="5f5d6-109">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="5f5d6-110">진행 이미지의 이진 표현을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="5f5d6-110">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="5f5d6-111">[in, out] 요청 된 최대 크기 (바이트) `pbBlob`입니다.</span><span class="sxs-lookup"><span data-stu-id="5f5d6-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="5f5d6-112">반환 시의 `pbBlob`실제 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="5f5d6-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f5d6-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="5f5d6-113">Return Value</span></span>  
 <span data-ttu-id="5f5d6-114">`true`성공적으로 완료 되 면 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="5f5d6-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f5d6-115">설명</span><span class="sxs-lookup"><span data-stu-id="5f5d6-115">Remarks</span></span>  
 <span data-ttu-id="5f5d6-116">`StrongNameGetBlobFromImage` 함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="5f5d6-116">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f5d6-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f5d6-117">Requirements</span></span>  
 <span data-ttu-id="5f5d6-118">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f5d6-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f5d6-119">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="5f5d6-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="5f5d6-120">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f5d6-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5f5d6-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f5d6-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f5d6-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="5f5d6-122">See also</span></span>

- [<span data-ttu-id="5f5d6-123">StrongNameGetBlobFromImage 메서드</span><span class="sxs-lookup"><span data-stu-id="5f5d6-123">StrongNameGetBlobFromImage Method</span></span>](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="5f5d6-124">StrongNameGetBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="5f5d6-124">StrongNameGetBlob Method</span></span>](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="5f5d6-125">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5f5d6-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
