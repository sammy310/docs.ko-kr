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
ms.openlocfilehash: 50e3cc6e677de45be9256a2a818ebd6ed7d8b843
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176918"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="389f2-102">StrongNameFreeBuffer 함수</span><span class="sxs-lookup"><span data-stu-id="389f2-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="389f2-103">[StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) 또는 [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)과 같은 강력한 이름 함수에 대한 이전 호출로 할당된 메모리를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="389f2-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="389f2-104">이 함수는 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="389f2-104">This function has been deprecated.</span></span> <span data-ttu-id="389f2-105">대신 [ICLRStrongName::StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="389f2-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="389f2-106">구문</span><span class="sxs-lookup"><span data-stu-id="389f2-106">Syntax</span></span>  
  
```cpp  
VOID StrongNameFreeBuffer (
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="389f2-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="389f2-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="389f2-108">【인】 해제할 메모리에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="389f2-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="389f2-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="389f2-109">Requirements</span></span>  
 <span data-ttu-id="389f2-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="389f2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="389f2-111">**헤더:** 스트롱네임</span><span class="sxs-lookup"><span data-stu-id="389f2-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="389f2-112">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="389f2-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="389f2-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="389f2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="389f2-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="389f2-114">See also</span></span>

- [<span data-ttu-id="389f2-115">StrongNameFreeBuffer 메서드</span><span class="sxs-lookup"><span data-stu-id="389f2-115">StrongNameFreeBuffer Method</span></span>](../hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="389f2-116">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="389f2-116">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
