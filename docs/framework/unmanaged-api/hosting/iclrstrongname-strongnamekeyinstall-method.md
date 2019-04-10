---
title: ICLRStrongName::StrongNameKeyInstall 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyInstall
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyInstall method [.NET Framework hosting]
- StrongNameKeyInstall method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5c15cf3b-164c-49d1-8e57-e42949d55acf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 415df9928572e095c529119bf2e726fa383577b0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224951"
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="8387a-102">ICLRStrongName::StrongNameKeyInstall 메서드</span><span class="sxs-lookup"><span data-stu-id="8387a-102">ICLRStrongName::StrongNameKeyInstall Method</span></span>
<span data-ttu-id="8387a-103">공개/개인 키 쌍을 컨테이너로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8387a-103">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8387a-104">구문</span><span class="sxs-lookup"><span data-stu-id="8387a-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8387a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8387a-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="8387a-106">[in] 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8387a-106">[in] The name of the key container.</span></span> `wszKeyContainer` <span data-ttu-id="8387a-107">비어 있지 않은 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8387a-107">must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="8387a-108">[in] 이진 키 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="8387a-108">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="8387a-109">[in] 크기 (바이트)의 `pbKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="8387a-109">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8387a-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="8387a-110">Return Value</span></span>  
 `S_OK` <span data-ttu-id="8387a-111">메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값을 (참조 [일반적인 HRESULT 값](https://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="8387a-111">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8387a-112">설명</span><span class="sxs-lookup"><span data-stu-id="8387a-112">Remarks</span></span>  
 <span data-ttu-id="8387a-113">사용 된 [iclrstrongname:: Strongnamekeydelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) 키 컨테이너를 삭제 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="8387a-113">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8387a-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8387a-114">Requirements</span></span>  
 <span data-ttu-id="8387a-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8387a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8387a-116">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="8387a-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8387a-117">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8387a-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="8387a-118">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="8387a-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8387a-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="8387a-119">See also</span></span>

- [<span data-ttu-id="8387a-120">StrongNameKeyDelete 메서드</span><span class="sxs-lookup"><span data-stu-id="8387a-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="8387a-121">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8387a-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
