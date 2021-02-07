---
description: '자세히 알아보기: ISymUnmanagedWriter:: UsingNamespace 메서드'
title: ISymUnmanagedWriter::UsingNamespace 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.UsingNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::UsingNamespace
helpviewer_keywords:
- UsingNamespace method [.NET Framework debugging]
- ISymUnmanagedWriter::UsingNamespace method [.NET Framework debugging]
ms.assetid: 8d746e0a-d158-4983-88da-db0a0856bc0b
topic_type:
- apiref
ms.openlocfilehash: e7d56cded125aac6154d4315c587f58f946a9a82
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761956"
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="8d3c1-103">ISymUnmanagedWriter::UsingNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="8d3c1-103">ISymUnmanagedWriter::UsingNamespace Method</span></span>

<span data-ttu-id="8d3c1-104">지정 된 정규화 된 네임 스페이스 이름이 현재 열려 있는 어휘 범위 내에서 사용 되 고 있음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d3c1-104">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="8d3c1-105">네임 스페이스는 현재 열려 있는 범위에서 상속 되는 모든 범위 내에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d3c1-105">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="8d3c1-106">현재 범위를 닫으면 네임 스페이스 사용도 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d3c1-106">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d3c1-107">구문</span><span class="sxs-lookup"><span data-stu-id="8d3c1-107">Syntax</span></span>  
  
```cpp  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d3c1-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8d3c1-108">Parameters</span></span>  

 `fullName`  
 <span data-ttu-id="8d3c1-109">진행 네임 스페이스의 정규화 된 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8d3c1-109">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8d3c1-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="8d3c1-110">Return Value</span></span>  

 <span data-ttu-id="8d3c1-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="8d3c1-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d3c1-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8d3c1-112">Requirements</span></span>  

 <span data-ttu-id="8d3c1-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="8d3c1-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d3c1-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d3c1-114">See also</span></span>

- [<span data-ttu-id="8d3c1-115">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8d3c1-115">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
