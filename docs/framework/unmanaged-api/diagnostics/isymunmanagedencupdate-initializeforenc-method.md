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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 135ae21c2281c545aa701ac2a22a43cea63f5242
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120330"
---
# <a name="isymunmanagedencupdateinitializeforenc-method"></a><span data-ttu-id="a0ae3-102">ISymUnmanagedENCUpdate::InitializeForEnc 메서드</span><span class="sxs-lookup"><span data-stu-id="a0ae3-102">ISymUnmanagedENCUpdate::InitializeForEnc Method</span></span>
<span data-ttu-id="a0ae3-103">첫 번째 호출 하기 전에 계산 메서드 경계를 허용 합니다 [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="a0ae3-103">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0ae3-104">구문</span><span class="sxs-lookup"><span data-stu-id="a0ae3-104">Syntax</span></span>  
  
```  
HRESULT InitializeForEnc();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a0ae3-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="a0ae3-105">Return Value</span></span>  
 <span data-ttu-id="a0ae3-106">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a0ae3-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0ae3-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a0ae3-107">Requirements</span></span>  
 <span data-ttu-id="a0ae3-108">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a0ae3-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0ae3-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="a0ae3-109">See also</span></span>

- [<span data-ttu-id="a0ae3-110">ISymUnmanagedENCUpdate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a0ae3-110">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
