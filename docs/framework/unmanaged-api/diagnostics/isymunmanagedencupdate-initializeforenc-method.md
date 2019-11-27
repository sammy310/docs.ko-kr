---
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
ms.openlocfilehash: 220788a38cd0ff90fed3b681a161c579206cf805
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449023"
---
# <a name="isymunmanagedencupdateinitializeforenc-method"></a><span data-ttu-id="4a0b1-102">ISymUnmanagedENCUpdate::InitializeForEnc 메서드</span><span class="sxs-lookup"><span data-stu-id="4a0b1-102">ISymUnmanagedENCUpdate::InitializeForEnc Method</span></span>
<span data-ttu-id="4a0b1-103">[ISymUnmanagedENCUpdate:: UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) 메서드를 처음으로 호출 하기 전에 메서드 경계를 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0b1-103">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a0b1-104">구문</span><span class="sxs-lookup"><span data-stu-id="4a0b1-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForEnc();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4a0b1-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="4a0b1-105">Return Value</span></span>  
 <span data-ttu-id="4a0b1-106">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="4a0b1-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a0b1-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a0b1-107">Requirements</span></span>  
 <span data-ttu-id="4a0b1-108">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="4a0b1-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a0b1-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a0b1-109">See also</span></span>

- [<span data-ttu-id="4a0b1-110">ISymUnmanagedENCUpdate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a0b1-110">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
