---
description: '자세히 알아보기: ISymUnmanagedNamespace:: GetName 메서드'
title: ISymUnmanagedNamespace::GetName 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetName
helpviewer_keywords:
- ISymUnmanagedNamespace::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 657bf91d-005a-4ea4-9298-04d1291c0bc3
topic_type:
- apiref
ms.openlocfilehash: f4d366363cd089995f98039389f59077e949fb79
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721218"
---
# <a name="isymunmanagednamespacegetname-method"></a><span data-ttu-id="3a1c4-103">ISymUnmanagedNamespace::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="3a1c4-103">ISymUnmanagedNamespace::GetName Method</span></span>

<span data-ttu-id="3a1c4-104">이 네임 스페이스의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3a1c4-104">Gets the name of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a1c4-105">구문</span><span class="sxs-lookup"><span data-stu-id="3a1c4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a1c4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3a1c4-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="3a1c4-107">진행 `ULONG32` 버퍼의 크기를 나타내는입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="3a1c4-107">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="3a1c4-108">제한이 `ULONG32` Null 종료를 포함 하 여 네임 스페이스 이름을 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3a1c4-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespace name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="3a1c4-109">제한이 네임 스페이스 이름을 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3a1c4-109">[out] A pointer to a buffer that contains the namespace name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a1c4-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="3a1c4-110">Return Value</span></span>  

 <span data-ttu-id="3a1c4-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="3a1c4-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a1c4-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a1c4-112">Requirements</span></span>  

 <span data-ttu-id="3a1c4-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="3a1c4-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a1c4-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a1c4-114">See also</span></span>

- [<span data-ttu-id="3a1c4-115">ISymUnmanagedNamespace 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3a1c4-115">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
