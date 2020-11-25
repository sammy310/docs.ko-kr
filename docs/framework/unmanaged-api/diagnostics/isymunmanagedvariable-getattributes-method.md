---
title: ISymUnmanagedVariable::GetAttributes 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAttributes
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAttributes
helpviewer_keywords:
- GetAttributes method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAttributes method [.NET Framework debugging]
ms.assetid: 80f168af-a6a6-4c8f-b9e6-8a82dc834ed5
topic_type:
- apiref
ms.openlocfilehash: 1142dbb83693f6104ba6e22e174ce02fb92997a6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726901"
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="46073-102">ISymUnmanagedVariable::GetAttributes 메서드</span><span class="sxs-lookup"><span data-stu-id="46073-102">ISymUnmanagedVariable::GetAttributes Method</span></span>

<span data-ttu-id="46073-103">이 변수에 대 한 특성 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="46073-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46073-104">구문</span><span class="sxs-lookup"><span data-stu-id="46073-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46073-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46073-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="46073-106">제한이 특성을 수신 하는에 대 한 포인터 `ULONG32` 입니다.</span><span class="sxs-lookup"><span data-stu-id="46073-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="46073-107">반환 되는 값은 [Corsymvarflag](corsymvarflag-enumeration.md) 열거형에 정의 된 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="46073-107">The returned value will be one of the values defined in the [CorSymVarFlag](corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46073-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="46073-108">Return Value</span></span>  

 <span data-ttu-id="46073-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="46073-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46073-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="46073-110">Requirements</span></span>  

 <span data-ttu-id="46073-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="46073-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46073-112">참조</span><span class="sxs-lookup"><span data-stu-id="46073-112">See also</span></span>

- [<span data-ttu-id="46073-113">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46073-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
