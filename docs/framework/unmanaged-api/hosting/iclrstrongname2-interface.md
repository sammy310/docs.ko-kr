---
title: ICLRStrongName2 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRStrongName2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName2
helpviewer_keywords:
- ICLRStrongName2 interface [.NET Framework hosting]
ms.assetid: 9f098a74-201e-4628-a468-8dee9ab99b4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bf9e3d2df8f507e118b393007c3958358a830cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763726"
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="33007-102">ICLRStrongName2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="33007-102">ICLRStrongName2 Interface</span></span>
<span data-ttu-id="33007-103">보안 해시 알고리즘 (SHA-256, SHA-384 및 SHA-512)의 sha-2 그룹을 사용 하 여 강력한 이름을 만드는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="33007-103">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33007-104">메서드</span><span class="sxs-lookup"><span data-stu-id="33007-104">Methods</span></span>  
  
|<span data-ttu-id="33007-105">메서드</span><span class="sxs-lookup"><span data-stu-id="33007-105">Method</span></span>|<span data-ttu-id="33007-106">설명</span><span class="sxs-lookup"><span data-stu-id="33007-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33007-107">StrongNameGetPublicKeyEx 메서드</span><span class="sxs-lookup"><span data-stu-id="33007-107">StrongNameGetPublicKeyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|<span data-ttu-id="33007-108">공개/개인 키 쌍에서 공개 키를 가져옵니다 하 고 해시 알고리즘 및 서명 알고리즘을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="33007-108">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="33007-109">StrongNameSignatureVerificationEx2 메서드</span><span class="sxs-lookup"><span data-stu-id="33007-109">StrongNameSignatureVerificationEx2 Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|<span data-ttu-id="33007-110">강력한 이름의 어셈블리의 서명을 확인 하 고 실제 키에 대 한 매핑을 ECMA 키에서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="33007-110">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33007-111">설명</span><span class="sxs-lookup"><span data-stu-id="33007-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33007-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="33007-112">Requirements</span></span>  
 <span data-ttu-id="33007-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="33007-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33007-114">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="33007-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="33007-115">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="33007-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33007-116">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33007-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
