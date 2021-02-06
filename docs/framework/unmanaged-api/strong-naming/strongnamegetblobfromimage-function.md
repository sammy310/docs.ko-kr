---
description: '자세히 알아보기: StrongNameGetBlobFromImage 함수'
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
ms.openlocfilehash: c68d6914d47fbb711c49c1e8432cae1bf33e771f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636353"
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="20ab3-103">StrongNameGetBlobFromImage 함수</span><span class="sxs-lookup"><span data-stu-id="20ab3-103">StrongNameGetBlobFromImage Function</span></span>

<span data-ttu-id="20ab3-104">지정된 메모리 주소에 있는 어셈블리 이미지의 이진 표현을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="20ab3-104">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="20ab3-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20ab3-105">This function has been deprecated.</span></span> <span data-ttu-id="20ab3-106">대신 [ICLRStrongName:: StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20ab3-106">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20ab3-107">구문</span><span class="sxs-lookup"><span data-stu-id="20ab3-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20ab3-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="20ab3-108">Parameters</span></span>  

 `pbBase`  
 <span data-ttu-id="20ab3-109">진행 매핑된 어셈블리 매니페스트의 메모리 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="20ab3-109">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="20ab3-110">진행 에 있는 이미지의 크기 (바이트)입니다 `pbBase` .</span><span class="sxs-lookup"><span data-stu-id="20ab3-110">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="20ab3-111">진행 이미지의 이진 표현을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="20ab3-111">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="20ab3-112">[in, out] 요청 된 최대 크기 (바이트)입니다 `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="20ab3-112">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="20ab3-113">반환 시의 실제 크기 (바이트)입니다 `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="20ab3-113">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20ab3-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="20ab3-114">Return Value</span></span>  

 <span data-ttu-id="20ab3-115">`true` 성공적으로 완료 되 면 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="20ab3-115">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20ab3-116">설명</span><span class="sxs-lookup"><span data-stu-id="20ab3-116">Remarks</span></span>  

 <span data-ttu-id="20ab3-117">`StrongNameGetBlobFromImage`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="20ab3-117">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20ab3-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="20ab3-118">Requirements</span></span>  

 <span data-ttu-id="20ab3-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20ab3-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20ab3-120">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="20ab3-120">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="20ab3-121">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20ab3-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="20ab3-122">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20ab3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20ab3-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20ab3-123">See also</span></span>

- [<span data-ttu-id="20ab3-124">StrongNameGetBlobFromImage 메서드</span><span class="sxs-lookup"><span data-stu-id="20ab3-124">StrongNameGetBlobFromImage Method</span></span>](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="20ab3-125">StrongNameGetBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="20ab3-125">StrongNameGetBlob Method</span></span>](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="20ab3-126">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="20ab3-126">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
