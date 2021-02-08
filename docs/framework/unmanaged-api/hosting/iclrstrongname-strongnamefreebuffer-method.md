---
description: '자세히 알아보기: ICLRStrongName:: StrongNameFreeBuffer 메서드'
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
ms.openlocfilehash: 8b65b75b92dd259c6919cfac9bc097066f552aba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799652"
---
# <a name="iclrstrongnamestrongnamefreebuffer-method"></a><span data-ttu-id="f9bf4-103">ICLRStrongName::StrongNameFreeBuffer 메서드</span><span class="sxs-lookup"><span data-stu-id="f9bf4-103">ICLRStrongName::StrongNameFreeBuffer Method</span></span>

<span data-ttu-id="f9bf4-104">[ICLRStrongName:: StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName:: StrongNameTokenFromPublicKey](iclrstrongname-strongnametokenfrompublickey-method.md)또는 [ICLRStrongName:: StrongNameSignatureGeneration](iclrstrongname-strongnamesignaturegeneration-method.md)와 같은 강력한 이름 메서드에 대 한 이전 호출로 할당 된 메모리를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-104">Frees memory that was allocated with a previous call to a strong name method such as [ICLRStrongName::StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameTokenFromPublicKey](iclrstrongname-strongnametokenfrompublickey-method.md), or [ICLRStrongName::StrongNameSignatureGeneration](iclrstrongname-strongnamesignaturegeneration-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9bf4-105">구문</span><span class="sxs-lookup"><span data-stu-id="f9bf4-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameFreeBuffer (
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9bf4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f9bf4-106">Parameters</span></span>  

 `pbMemory`  
 <span data-ttu-id="f9bf4-107">진행 해제할 메모리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-107">[in] A pointer to the memory to free.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f9bf4-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="f9bf4-108">Return Value</span></span>  

 <span data-ttu-id="f9bf4-109">`S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="f9bf4-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9bf4-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f9bf4-110">Requirements</span></span>  

 <span data-ttu-id="f9bf4-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9bf4-112">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="f9bf4-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f9bf4-113">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9bf4-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f9bf4-114">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9bf4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9bf4-115">참조</span><span class="sxs-lookup"><span data-stu-id="f9bf4-115">See also</span></span>

- [<span data-ttu-id="f9bf4-116">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f9bf4-116">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
