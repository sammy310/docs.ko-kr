---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 639664c6ce5714b554f30bff2569a12bf48d1671
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799131"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="b6e63-102">StrongNameFreeBuffer 함수</span><span class="sxs-lookup"><span data-stu-id="b6e63-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="b6e63-103">[StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) 또는 [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)과 같은 강력한 이름 함수에 대한 이전 호출로 할당된 메모리를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e63-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="b6e63-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e63-104">This function has been deprecated.</span></span> <span data-ttu-id="b6e63-105">대신 [ICLRStrongName:: StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e63-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6e63-106">구문</span><span class="sxs-lookup"><span data-stu-id="b6e63-106">Syntax</span></span>  
  
```cpp  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6e63-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b6e63-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="b6e63-108">진행 해제할 메모리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e63-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6e63-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b6e63-109">Requirements</span></span>  
 <span data-ttu-id="b6e63-110">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b6e63-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6e63-111">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="b6e63-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="b6e63-112">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e63-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b6e63-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6e63-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6e63-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="b6e63-114">See also</span></span>

- [<span data-ttu-id="b6e63-115">StrongNameFreeBuffer 메서드</span><span class="sxs-lookup"><span data-stu-id="b6e63-115">StrongNameFreeBuffer Method</span></span>](../hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="b6e63-116">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6e63-116">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
