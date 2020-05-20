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
ms.openlocfilehash: 8ee4c1bffccb44d15fa53eb3d4d6c0fcdc3e7697
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614970"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="3a712-102">ISymUnmanagedReader::GetMethodVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="3a712-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="3a712-103">메서드 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3a712-103">Gets the method version.</span></span> <span data-ttu-id="3a712-104">메서드 버전은 1에서 시작 하 고 메서드를 다시 컴파일할 때마다 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a712-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="3a712-105">메서드를 변경 하지 않고도 다시 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a712-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a712-106">구문</span><span class="sxs-lookup"><span data-stu-id="3a712-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a712-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3a712-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="3a712-108">진행 버전을 가져올 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="3a712-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="3a712-109">제한이 메서드 버전을 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3a712-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a712-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="3a712-110">Return Value</span></span>  
 <span data-ttu-id="3a712-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="3a712-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a712-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a712-112">Requirements</span></span>  
 <span data-ttu-id="3a712-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="3a712-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a712-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a712-114">See also</span></span>

- [<span data-ttu-id="3a712-115">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3a712-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
