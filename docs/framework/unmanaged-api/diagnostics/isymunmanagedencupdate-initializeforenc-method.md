---
description: '자세히 알아보기: ISymUnmanagedENCUpdate:: InitializeForEnc 메서드'
title: ISymUnmanagedENCUpdate::InitializeForEnc 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.InitializeForEnc
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::InitializeForEnc
helpviewer_keywords:
- ISymUnmanagedENCUpdate::InitializeForEnc method [.NET Framework debugging]
- InitializeForEnc method [.NET Framework debugging]
ms.assetid: 796b2154-b53c-4d07-9e67-80fd6064725a
topic_type:
- apiref
ms.openlocfilehash: 2b70554cc565f025dcf35e2a84523a5f9a6130f4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710103"
---
# <a name="isymunmanagedencupdateinitializeforenc-method"></a><span data-ttu-id="ac0a6-103">ISymUnmanagedENCUpdate::InitializeForEnc 메서드</span><span class="sxs-lookup"><span data-stu-id="ac0a6-103">ISymUnmanagedENCUpdate::InitializeForEnc Method</span></span>

<span data-ttu-id="ac0a6-104">[ISymUnmanagedENCUpdate:: UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) 메서드를 처음으로 호출 하기 전에 메서드 경계를 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0a6-104">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac0a6-105">구문</span><span class="sxs-lookup"><span data-stu-id="ac0a6-105">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForEnc();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ac0a6-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="ac0a6-106">Return Value</span></span>  

 <span data-ttu-id="ac0a6-107">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ac0a6-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac0a6-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ac0a6-108">Requirements</span></span>  

 <span data-ttu-id="ac0a6-109">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="ac0a6-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac0a6-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac0a6-110">See also</span></span>

- [<span data-ttu-id="ac0a6-111">ISymUnmanagedENCUpdate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac0a6-111">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
