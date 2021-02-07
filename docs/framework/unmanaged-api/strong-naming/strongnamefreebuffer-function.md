---
description: '자세히 알아보기: StrongNameFreeBuffer 함수'
title: StrongNameFreeBuffer 함수
ms.date: 03/30/2017
api_name:
- StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type:
- apiref
ms.openlocfilehash: fa1b1d7710a981c5284ee79d551cbf51ede285db
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736455"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="d7081-103">StrongNameFreeBuffer 함수</span><span class="sxs-lookup"><span data-stu-id="d7081-103">StrongNameFreeBuffer Function</span></span>

<span data-ttu-id="d7081-104">[StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) 또는 [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)과 같은 강력한 이름 함수에 대한 이전 호출로 할당된 메모리를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="d7081-104">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="d7081-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7081-105">This function has been deprecated.</span></span> <span data-ttu-id="d7081-106">대신 [ICLRStrongName:: StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7081-106">Use the [ICLRStrongName::StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7081-107">구문</span><span class="sxs-lookup"><span data-stu-id="d7081-107">Syntax</span></span>  
  
```cpp  
VOID StrongNameFreeBuffer (
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7081-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d7081-108">Parameters</span></span>  

 `pbMemory`  
 <span data-ttu-id="d7081-109">진행 해제할 메모리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d7081-109">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7081-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7081-110">Requirements</span></span>  

 <span data-ttu-id="d7081-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7081-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7081-112">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="d7081-112">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d7081-113">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7081-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d7081-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7081-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7081-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7081-115">See also</span></span>

- [<span data-ttu-id="d7081-116">StrongNameFreeBuffer 메서드</span><span class="sxs-lookup"><span data-stu-id="d7081-116">StrongNameFreeBuffer Method</span></span>](../hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="d7081-117">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7081-117">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
