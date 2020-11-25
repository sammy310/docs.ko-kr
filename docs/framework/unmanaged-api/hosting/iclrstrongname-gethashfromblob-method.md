---
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
ms.openlocfilehash: 6b67aed90585f57d2635bb1a22d3e009edf01159
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714811"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="f6128-102">ICLRStrongName::GetHashFromBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="f6128-102">ICLRStrongName::GetHashFromBlob Method</span></span>

<span data-ttu-id="f6128-103">지정된 해시 알고리즘을 사용하여 지정된 메모리 주소에 있는 어셈블리의 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f6128-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6128-104">구문</span><span class="sxs-lookup"><span data-stu-id="f6128-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f6128-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f6128-105">Parameters</span></span>  

 `pbBlob`  
 <span data-ttu-id="f6128-106">진행 해시할 메모리 블록의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f6128-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="f6128-107">진행 메모리 블록의 길이 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="f6128-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="f6128-108">[in, out] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="f6128-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="f6128-109">기본 알고리즘에는 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6128-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="f6128-110">제한이 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="f6128-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="f6128-111">진행 요청 된 최대 크기 `pbHash` 입니다.</span><span class="sxs-lookup"><span data-stu-id="f6128-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="f6128-112">제한이 반환 된의 크기 (바이트)입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="f6128-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6128-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="f6128-113">Return Value</span></span>  

 <span data-ttu-id="f6128-114">`S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="f6128-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6128-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f6128-115">Requirements</span></span>  

 <span data-ttu-id="f6128-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f6128-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6128-117">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="f6128-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f6128-118">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6128-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f6128-119">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6128-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6128-120">참조</span><span class="sxs-lookup"><span data-stu-id="f6128-120">See also</span></span>

- [<span data-ttu-id="f6128-121">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f6128-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
