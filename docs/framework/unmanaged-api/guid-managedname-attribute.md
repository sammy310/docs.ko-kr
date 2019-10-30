---
title: GUID_ManagedName 특성
ms.date: 03/30/2017
api_name:
- GUID_ManagedName
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GUID_ManagedName
helpviewer_keywords:
- GUID_ManagedName attribute
ms.assetid: 11e18095-e444-47bc-aff6-b887ac5dc01e
topic_type:
- apiref
ms.openlocfilehash: 9d30c8fe71a0dfff7de9bb2f43b325cbb8016a23
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123047"
---
# <a name="guid_managedname-attribute"></a>GUID_ManagedName 특성
COM (구성 요소 개체 모델) 라이브러리의 관리 되는 네임 스페이스 이름을 지정 하는 사용자 지정 인터페이스 특성을 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```idl
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
## <a name="parameters"></a>매개 변수  
 `value`  
 라이브러리에 대 한 관리 되는 네임 스페이스 이름입니다.  
  
## <a name="definition"></a>정의  
 `GUID_ManagedName`는 Cor에서 다음과 같이 정의 됩니다.  
  
```cpp
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a>주의  
 사용자 지정 인터페이스 특성은 형식 라이브러리의 개체에 대 한 메타 데이터를 정의 합니다.  
  
 <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> 또는 <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType>를 사용 하 여 특성에서 관리 되는 이름을 검색 합니다.  
  
 자세한 내용은 시각적 C++ 참조 설명서의 [인터페이스 특성](/cpp/windows/attributes/interface-attributes) 을 참조 하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `GUID_ManagedName` 특성을 사용 하는 라이브러리 정의를 보여 줍니다.  
  
```idl
[  
   ...  
   custom(GUID_ManagedName, Microsoft.VisualStudio.CommandBars.dll")  
]  
library Microsoft_VisualStudio_CommandBars  
{  
   ...  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** Cor
