---
description: '자세히 알아보기: ICLRStrongName:: StrongNameGetBlobFromImage 메서드'
title: ICLRStrongName::StrongNameGetBlobFromImage 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetBlobFromImage method [.NET Framework hosting]
ms.assetid: 0f5a2ec8-e776-4fd8-bda6-937b6834575a
topic_type:
- apiref
ms.openlocfilehash: 32f04e21f1f08f3872ccdd27a64f39ea29d7e060
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799618"
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a><span data-ttu-id="0f7ff-103">ICLRStrongName::StrongNameGetBlobFromImage 메서드</span><span class="sxs-lookup"><span data-stu-id="0f7ff-103">ICLRStrongName::StrongNameGetBlobFromImage Method</span></span>

<span data-ttu-id="0f7ff-104">지정된 메모리 주소에 있는 어셈블리 이미지의 이진 표현을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f7ff-104">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f7ff-105">구문</span><span class="sxs-lookup"><span data-stu-id="0f7ff-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f7ff-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0f7ff-106">Parameters</span></span>  

 `pbBase`  
 <span data-ttu-id="0f7ff-107">진행 매핑된 어셈블리 매니페스트의 메모리 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="0f7ff-107">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="0f7ff-108">진행 에 있는 이미지의 크기 (바이트)입니다 `pbBase` .</span><span class="sxs-lookup"><span data-stu-id="0f7ff-108">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="0f7ff-109">진행 이미지의 이진 표현을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="0f7ff-109">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="0f7ff-110">[in, out] 요청 된 최대 크기 (바이트)입니다 `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="0f7ff-110">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="0f7ff-111">반환 시의 실제 크기 (바이트)입니다 `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="0f7ff-111">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f7ff-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="0f7ff-112">Return Value</span></span>  

 <span data-ttu-id="0f7ff-113">`S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="0f7ff-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f7ff-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f7ff-114">Requirements</span></span>  

 <span data-ttu-id="0f7ff-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f7ff-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f7ff-116">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="0f7ff-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0f7ff-117">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f7ff-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f7ff-118">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f7ff-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f7ff-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f7ff-119">See also</span></span>

- [<span data-ttu-id="0f7ff-120">StrongNameGetBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="0f7ff-120">StrongNameGetBlob Method</span></span>](iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="0f7ff-121">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f7ff-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
