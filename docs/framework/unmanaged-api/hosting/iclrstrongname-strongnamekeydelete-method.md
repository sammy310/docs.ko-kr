---
description: '자세히 알아보기: ICLRStrongName:: StrongNameKeyDelete 메서드'
title: ICLRStrongName::StrongNameKeyDelete 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyDelete method [.NET Framework hosting]
ms.assetid: 0163412f-f617-4428-89e0-03992fec31e8
topic_type:
- apiref
ms.openlocfilehash: 5b782785921eb24394db53d29a66600a3867b489
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799579"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="2483f-103">ICLRStrongName::StrongNameKeyDelete 메서드</span><span class="sxs-lookup"><span data-stu-id="2483f-103">ICLRStrongName::StrongNameKeyDelete Method</span></span>

<span data-ttu-id="2483f-104">지정된 키 컨테이너를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="2483f-104">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2483f-105">구문</span><span class="sxs-lookup"><span data-stu-id="2483f-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2483f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2483f-106">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="2483f-107">진행 삭제할 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2483f-107">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2483f-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="2483f-108">Return Value</span></span>  

 <span data-ttu-id="2483f-109">`S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="2483f-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2483f-110">설명</span><span class="sxs-lookup"><span data-stu-id="2483f-110">Remarks</span></span>  

 <span data-ttu-id="2483f-111">[ICLRStrongName:: StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md) 메서드를 사용 하 여 공용/개인 키 쌍을 컨테이너로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2483f-111">Use the [ICLRStrongName::StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2483f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2483f-112">Requirements</span></span>  

 <span data-ttu-id="2483f-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2483f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2483f-114">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="2483f-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2483f-115">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2483f-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2483f-116">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2483f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2483f-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2483f-117">See also</span></span>

- [<span data-ttu-id="2483f-118">StrongNameKeyInstall 메서드</span><span class="sxs-lookup"><span data-stu-id="2483f-118">StrongNameKeyInstall Method</span></span>](iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="2483f-119">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2483f-119">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
