---
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
ms.openlocfilehash: 8db3b1854e334cef4d91d21eb5f666ba2e88fc2e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135057"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="02e47-102">ICLRStrongName::StrongNameHashSize 메서드</span><span class="sxs-lookup"><span data-stu-id="02e47-102">ICLRStrongName::StrongNameHashSize Method</span></span>
<span data-ttu-id="02e47-103">지정된 해시 알고리즘을 사용하여 해시에 필요한 버퍼 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="02e47-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02e47-104">구문</span><span class="sxs-lookup"><span data-stu-id="02e47-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02e47-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="02e47-105">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="02e47-106">진행 버퍼 크기를 계산 하는 데 사용 되는 해시 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="02e47-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="02e47-107">제한이 반환 된 버퍼 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="02e47-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02e47-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="02e47-108">Return Value</span></span>  
 <span data-ttu-id="02e47-109">메서드가 성공적으로 완료 되 면 `S_OK` 하 고, 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](https://go.microsoft.com/fwlink/?LinkId=213878) 참조).</span><span class="sxs-lookup"><span data-stu-id="02e47-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02e47-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02e47-110">Requirements</span></span>  
 <span data-ttu-id="02e47-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02e47-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02e47-112">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="02e47-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="02e47-113">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02e47-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02e47-114">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02e47-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02e47-115">참조</span><span class="sxs-lookup"><span data-stu-id="02e47-115">See also</span></span>

- [<span data-ttu-id="02e47-116">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02e47-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
