---
title: ICLRAssemblyIdentityManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager
helpviewer_keywords:
- ICLRAssemblyIdentityManager interface [.NET Framework hosting]
ms.assetid: 6a81c6fe-cc22-4062-ae27-d6eeee03a7b9
topic_type:
- apiref
ms.openlocfilehash: f06c8228d5eb850c0d5ff94d12be03d7fb75023b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615919"
---
# <a name="iclrassemblyidentitymanager-interface"></a>ICLRAssemblyIdentityManager 인터페이스
호스트와 어셈블리에 대 한 CLR (공용 언어 런타임) 간의 통신을 지 원하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetBindingIdentityFromFile 메서드](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|지정 된 파일 경로에서 어셈블리의 어셈블리 id 바인딩 데이터를 가져옵니다.|  
|[GetBindingIdentityFromStream 메서드](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|지정 된 스트림의 어셈블리에 대 한 정식 어셈블리 id 데이터를 가져옵니다.|  
|[GetCLRAssemblyReferenceList 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|제공 된 부분 어셈블리 id 목록에서 [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) 인스턴스를 가져옵니다.|  
|[GetProbingAssembliesFromReference 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|지정 된 id를 사용 하 여 어셈블리에서 참조 하는 어셈블리 id의 [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) 열거자를 가져옵니다.|  
|[GetReferencedAssembliesFromFile 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|지정 된 파일 경로에서 어셈블리가 참조 하는 어셈블리의 목록을 포함 하는 [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) 인스턴스를 가져옵니다.|  
|[GetReferencedAssembliesFromStream 메서드](iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|지정 된 스트림의 어셈블리에서 참조 하는 어셈블리 `ICLRReferenceAssemblyEnum` 에 대 한 어셈블리 id 데이터를 포함 하는 개체에 대 한 포인터를 가져옵니다.|  
|[IsStronglyNamed 메서드](iclrassemblyidentitymanager-isstronglynamed-method.md)|지정 된 어셈블리에 강력한 이름이 지정 되었는지 여부를 나타내는 값을 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 를 사용 `ICLRAssemblyIdentityManager` 하 여 인스턴스를 가져오고 `ICLRAssemblyReferenceList` 어셈블리 id를 열거 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRAssemblyReferenceList 인터페이스](iclrassemblyreferencelist-interface.md)
- [ICLRProbingAssemblyEnum 인터페이스](iclrprobingassemblyenum-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
