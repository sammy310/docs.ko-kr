---
description: '자세히 알아보기: ICLRStrongName:: StrongNameKeyInstall 메서드'
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
ms.openlocfilehash: 8f9e7bfebff555a6430a3970c8ee1c481e341f58
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799514"
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="40304-103">ICLRStrongName::StrongNameKeyInstall 메서드</span><span class="sxs-lookup"><span data-stu-id="40304-103">ICLRStrongName::StrongNameKeyInstall Method</span></span>

<span data-ttu-id="40304-104">퍼블릭/프라이빗 키 쌍을 컨테이너로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="40304-104">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40304-105">구문</span><span class="sxs-lookup"><span data-stu-id="40304-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40304-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="40304-106">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="40304-107">진행 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="40304-107">[in] The name of the key container.</span></span> <span data-ttu-id="40304-108">`wszKeyContainer` 비어 있지 않은 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40304-108">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="40304-109">진행 이진 키 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="40304-109">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="40304-110">진행 의 크기 (바이트)입니다 `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="40304-110">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40304-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="40304-111">Return Value</span></span>  

 <span data-ttu-id="40304-112">`S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="40304-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40304-113">설명</span><span class="sxs-lookup"><span data-stu-id="40304-113">Remarks</span></span>  

 <span data-ttu-id="40304-114">[ICLRStrongName:: StrongNameKeyDelete](iclrstrongname-strongnamekeydelete-method.md) 메서드를 사용 하 여 키 컨테이너를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="40304-114">Use the [ICLRStrongName::StrongNameKeyDelete](iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40304-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="40304-115">Requirements</span></span>  

 <span data-ttu-id="40304-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40304-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40304-117">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="40304-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="40304-118">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40304-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40304-119">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40304-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40304-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="40304-120">See also</span></span>

- [<span data-ttu-id="40304-121">StrongNameKeyDelete 메서드</span><span class="sxs-lookup"><span data-stu-id="40304-121">StrongNameKeyDelete Method</span></span>](iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="40304-122">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40304-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
