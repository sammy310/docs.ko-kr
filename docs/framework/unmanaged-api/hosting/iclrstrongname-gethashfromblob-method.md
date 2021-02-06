---
description: '자세히 알아보기: ICLRStrongName:: GetHashFromBlob 메서드'
title: ICLRStrongName::GetHashFromBlob 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromBlob
helpviewer_keywords:
- ICLRStrongName::GetHashFromBlob method [.NET Framework hosting]
- GetHashFromBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: f91d0f89-f356-49ac-aafb-50fad963c13d
topic_type:
- apiref
ms.openlocfilehash: 20d03184f57e77741e656575038e426ee37968f9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637068"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="7bcc7-103">ICLRStrongName::GetHashFromBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="7bcc7-103">ICLRStrongName::GetHashFromBlob Method</span></span>

<span data-ttu-id="7bcc7-104">지정된 해시 알고리즘을 사용하여 지정된 메모리 주소에 있는 어셈블리의 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7bcc7-104">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bcc7-105">구문</span><span class="sxs-lookup"><span data-stu-id="7bcc7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bcc7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7bcc7-106">Parameters</span></span>  

 `pbBlob`  
 <span data-ttu-id="7bcc7-107">진행 해시할 메모리 블록의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7bcc7-107">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="7bcc7-108">진행 메모리 블록의 길이 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="7bcc7-108">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="7bcc7-109">[in, out] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="7bcc7-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="7bcc7-110">기본 알고리즘에는 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bcc7-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="7bcc7-111">제한이 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="7bcc7-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="7bcc7-112">진행 요청 된 최대 크기 `pbHash` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7bcc7-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="7bcc7-113">제한이 반환 된의 크기 (바이트)입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="7bcc7-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7bcc7-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="7bcc7-114">Return Value</span></span>  

 <span data-ttu-id="7bcc7-115">`S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="7bcc7-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bcc7-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7bcc7-116">Requirements</span></span>  

 <span data-ttu-id="7bcc7-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7bcc7-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bcc7-118">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="7bcc7-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7bcc7-119">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bcc7-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7bcc7-120">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bcc7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bcc7-121">참조</span><span class="sxs-lookup"><span data-stu-id="7bcc7-121">See also</span></span>

- [<span data-ttu-id="7bcc7-122">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7bcc7-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
