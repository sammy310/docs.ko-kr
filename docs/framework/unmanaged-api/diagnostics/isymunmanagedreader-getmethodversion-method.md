---
title: ISymUnmanagedReader::GetMethodVersion 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
ms.openlocfilehash: fcaf748413321f684336543e60f735af69894b51
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436004"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="02d7d-102">ISymUnmanagedReader::GetMethodVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="02d7d-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="02d7d-103">메서드 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="02d7d-103">Gets the method version.</span></span> <span data-ttu-id="02d7d-104">메서드 버전은 1에서 시작 하 고 메서드를 다시 컴파일할 때마다 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d7d-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="02d7d-105">메서드를 변경 하지 않고도 다시 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d7d-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02d7d-106">구문</span><span class="sxs-lookup"><span data-stu-id="02d7d-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02d7d-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="02d7d-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="02d7d-108">진행 버전을 가져올 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="02d7d-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="02d7d-109">제한이 메서드 버전을 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="02d7d-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02d7d-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="02d7d-110">Return Value</span></span>  
 <span data-ttu-id="02d7d-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="02d7d-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02d7d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02d7d-112">Requirements</span></span>  
 <span data-ttu-id="02d7d-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="02d7d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02d7d-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02d7d-114">See also</span></span>

- [<span data-ttu-id="02d7d-115">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02d7d-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
