---
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
ms.openlocfilehash: eca1137fb607d64e8645de5b0afc7ca391eac763
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699263"
---
# <a name="isymunmanagednamespacegetname-method"></a><span data-ttu-id="fd29b-102">ISymUnmanagedNamespace::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="fd29b-102">ISymUnmanagedNamespace::GetName Method</span></span>

<span data-ttu-id="fd29b-103">이 네임 스페이스의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fd29b-103">Gets the name of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd29b-104">구문</span><span class="sxs-lookup"><span data-stu-id="fd29b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd29b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fd29b-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="fd29b-106">진행 `ULONG32` 버퍼의 크기를 나타내는입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="fd29b-106">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="fd29b-107">제한이 `ULONG32` Null 종료를 포함 하 여 네임 스페이스 이름을 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fd29b-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespace name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="fd29b-108">제한이 네임 스페이스 이름을 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fd29b-108">[out] A pointer to a buffer that contains the namespace name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd29b-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="fd29b-109">Return Value</span></span>  

 <span data-ttu-id="fd29b-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="fd29b-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd29b-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd29b-111">Requirements</span></span>  

 <span data-ttu-id="fd29b-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="fd29b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd29b-113">참조</span><span class="sxs-lookup"><span data-stu-id="fd29b-113">See also</span></span>

- [<span data-ttu-id="fd29b-114">ISymUnmanagedNamespace 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fd29b-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
