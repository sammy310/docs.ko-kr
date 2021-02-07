---
description: '자세히 알아보기: ISymUnmanagedVariable:: GetName 메서드'
title: ISymUnmanagedVariable::GetName 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetName
helpviewer_keywords:
- GetName method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetName method [.NET Framework debugging]
ms.assetid: eedf1ef0-9d4a-4847-a201-4e99572dfe5e
topic_type:
- apiref
ms.openlocfilehash: 88d8cf4c81200a30e2a102b63af2817fef2b50c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762788"
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="32586-103">ISymUnmanagedVariable::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="32586-103">ISymUnmanagedVariable::GetName Method</span></span>

<span data-ttu-id="32586-104">이 변수의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="32586-104">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32586-105">구문</span><span class="sxs-lookup"><span data-stu-id="32586-105">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32586-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="32586-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="32586-107">진행 매개 변수가 가리키는 버퍼의 길이입니다 `pcchName` .</span><span class="sxs-lookup"><span data-stu-id="32586-107">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="32586-108">제한이 `ULONG32` Null 종료를 포함 하 여 이름을 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="32586-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="32586-109">제한이 이름을 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="32586-109">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32586-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="32586-110">Return Value</span></span>  

 <span data-ttu-id="32586-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="32586-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32586-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32586-112">Requirements</span></span>  

 <span data-ttu-id="32586-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="32586-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32586-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32586-114">See also</span></span>

- [<span data-ttu-id="32586-115">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32586-115">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
