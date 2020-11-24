---
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
ms.openlocfilehash: 46345ae570673c9c9c0c58fb6edea1464ba8dd91
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671696"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="32af8-102">ICLRStrongName::StrongNameKeyDelete 메서드</span><span class="sxs-lookup"><span data-stu-id="32af8-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>

<span data-ttu-id="32af8-103">지정된 키 컨테이너를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="32af8-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32af8-104">구문</span><span class="sxs-lookup"><span data-stu-id="32af8-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32af8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="32af8-105">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="32af8-106">진행 삭제할 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="32af8-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32af8-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="32af8-107">Return Value</span></span>  

 <span data-ttu-id="32af8-108">`S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="32af8-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32af8-109">설명</span><span class="sxs-lookup"><span data-stu-id="32af8-109">Remarks</span></span>  

 <span data-ttu-id="32af8-110">[ICLRStrongName:: StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md) 메서드를 사용 하 여 공용/개인 키 쌍을 컨테이너로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="32af8-110">Use the [ICLRStrongName::StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32af8-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32af8-111">Requirements</span></span>  

 <span data-ttu-id="32af8-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32af8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32af8-113">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="32af8-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="32af8-114">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32af8-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32af8-115">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32af8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32af8-116">참조</span><span class="sxs-lookup"><span data-stu-id="32af8-116">See also</span></span>

- [<span data-ttu-id="32af8-117">StrongNameKeyInstall 메서드</span><span class="sxs-lookup"><span data-stu-id="32af8-117">StrongNameKeyInstall Method</span></span>](iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="32af8-118">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32af8-118">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
