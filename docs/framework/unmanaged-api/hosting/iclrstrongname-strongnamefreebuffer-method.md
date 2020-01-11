---
title: ICLRStrongName::StrongNameFreeBuffer 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameFreeBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameFreeBuffer method [.NET Framework hosting]
ms.assetid: 6148c508-bd1d-4a37-85c3-06ecb09cc857
topic_type:
- apiref
ms.openlocfilehash: 9aeac02e865214db8fec25621f1bf204a93b36f6
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901135"
---
# <a name="iclrstrongnamestrongnamefreebuffer-method"></a><span data-ttu-id="7ed28-102">ICLRStrongName::StrongNameFreeBuffer 메서드</span><span class="sxs-lookup"><span data-stu-id="7ed28-102">ICLRStrongName::StrongNameFreeBuffer Method</span></span>
<span data-ttu-id="7ed28-103">[ICLRStrongName:: StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName:: StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)또는 [ICLRStrongName:: StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)와 같은 강력한 이름 메서드에 대 한 이전 호출로 할당 된 메모리를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ed28-103">Frees memory that was allocated with a previous call to a strong name method such as [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), or [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ed28-104">구문</span><span class="sxs-lookup"><span data-stu-id="7ed28-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ed28-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7ed28-105">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="7ed28-106">진행 해제할 메모리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7ed28-106">[in] A pointer to the memory to free.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ed28-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="7ed28-107">Return Value</span></span>  
 <span data-ttu-id="7ed28-108">메서드가 성공적으로 완료 되 면 `S_OK` 하 고, 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="7ed28-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ed28-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7ed28-109">Requirements</span></span>  
 <span data-ttu-id="7ed28-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ed28-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ed28-111">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="7ed28-111">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7ed28-112">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ed28-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7ed28-113">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ed28-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ed28-114">참조</span><span class="sxs-lookup"><span data-stu-id="7ed28-114">See also</span></span>

- [<span data-ttu-id="7ed28-115">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7ed28-115">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
