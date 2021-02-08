---
description: '자세히 알아보기: ICLRStrongName:: StrongNameHashSize 메서드'
title: ICLRStrongName::StrongNameHashSize 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameHashSize
helpviewer_keywords:
- ICLRStrongName::StrongNameHashSize method [.NET Framework hosting]
- StrongNameHashSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 4a05ee56-08e4-4f3a-86a9-9b52083d5c0f
topic_type:
- apiref
ms.openlocfilehash: 74781f0eaec720a84a242e6a9637036408652601
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799592"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="3638e-103">ICLRStrongName::StrongNameHashSize 메서드</span><span class="sxs-lookup"><span data-stu-id="3638e-103">ICLRStrongName::StrongNameHashSize Method</span></span>

<span data-ttu-id="3638e-104">지정된 해시 알고리즘을 사용하여 해시에 필요한 버퍼 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3638e-104">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3638e-105">구문</span><span class="sxs-lookup"><span data-stu-id="3638e-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3638e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3638e-106">Parameters</span></span>  

 `ulHashAlg`  
 <span data-ttu-id="3638e-107">진행 버퍼 크기를 계산 하는 데 사용 되는 해시 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="3638e-107">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="3638e-108">제한이 반환 된 버퍼 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="3638e-108">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3638e-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="3638e-109">Return Value</span></span>  

 <span data-ttu-id="3638e-110">`S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="3638e-110">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3638e-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3638e-111">Requirements</span></span>  

 <span data-ttu-id="3638e-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3638e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3638e-113">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="3638e-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3638e-114">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3638e-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3638e-115">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3638e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3638e-116">참조</span><span class="sxs-lookup"><span data-stu-id="3638e-116">See also</span></span>

- [<span data-ttu-id="3638e-117">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3638e-117">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
