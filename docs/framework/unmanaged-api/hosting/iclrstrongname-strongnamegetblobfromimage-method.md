---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e13f0ebbdc4e5fe3974208f91ab57f86dd29c910
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748018"
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a><span data-ttu-id="8495a-102">ICLRStrongName::StrongNameGetBlobFromImage 메서드</span><span class="sxs-lookup"><span data-stu-id="8495a-102">ICLRStrongName::StrongNameGetBlobFromImage Method</span></span>
<span data-ttu-id="8495a-103">지정된 메모리 주소에 있는 어셈블리 이미지의 이진 표현을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8495a-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8495a-104">구문</span><span class="sxs-lookup"><span data-stu-id="8495a-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8495a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8495a-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="8495a-106">[in] 매핑된 어셈블리 매니페스트에 대 한 메모리 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8495a-106">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="8495a-107">[in] 크기 (바이트)의 이미지 `pbBase`합니다.</span><span class="sxs-lookup"><span data-stu-id="8495a-107">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="8495a-108">[in] 이미지의 이진 표현을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="8495a-108">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="8495a-109">[out에서] 최대 크기 (바이트), 요청한 `pbBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="8495a-109">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="8495a-110">실제 크기를 바이트 단위로 반환 될 때의 `pbBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="8495a-110">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8495a-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="8495a-111">Return Value</span></span>  
 <span data-ttu-id="8495a-112">`S_OK` 메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값을 (참조 [일반적인 HRESULT 값](https://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="8495a-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8495a-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8495a-113">Requirements</span></span>  
 <span data-ttu-id="8495a-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8495a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8495a-115">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="8495a-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8495a-116">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8495a-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8495a-117">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8495a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8495a-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="8495a-118">See also</span></span>

- [<span data-ttu-id="8495a-119">StrongNameGetBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="8495a-119">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="8495a-120">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8495a-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
