---
title: gcUnmanagedToManaged MDA
description: .NET에서 gcManagedToUnmanaged 관리 디버깅 길잡이를 검토 합니다. 이 MDA는 관리 코드로 전환 하는 동안 가비지 힙 손상이 발생 하 여 활성화할 수 있습니다.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GC unmanaged to managed
- transitioning threads unmanaged to managed code
- GcUnmanagedToManaged MDA
- threading [.NET Framework], garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
- unmanaged to managed garbage collection
ms.assetid: 103eb3a3-1cf0-4406-8a9a-a7798fdc22d1
ms.openlocfilehash: 61fbdbf0d3941aa3e876748ae4d76cd7ad0c0977
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244225"
---
# <a name="gcunmanagedtomanaged-mda"></a>gcUnmanagedToManaged MDA

`gcUnmanagedToManaged` MDA(관리 디버깅 도우미)는 위협이 비관리 코드에서 관리 코드로 전환될 때마다 가비지 수집을 발생시킵니다.  
  
## <a name="symptoms"></a>증상  

 COM 및 플랫폼 호출을 사용하여 관리되지 않는 사용자 구성 요소를 실행하는 애플리케이션은 CLR에서 비결정적 액세스 위반을 발생시킵니다.  
  
## <a name="cause"></a>원인  

 애플리케이션이 관리되지 않는 사용자 구성 요소를 실행하는 경우 해당 구성 요소로 인해 가비지 수집된 힙이 손상되었을 수 있습니다. 이 경우 가비지 수집기가 개체 그래프를 검색하려고 하면 CLR에서 액세스 위반이 발생합니다.  
  
## <a name="resolution"></a>해결 방법  

 이 도우미를 사용하도록 설정하면 관리되는 각 전환 전에 가비지 수집이 강제로 수행되어 관리되지 않는 구성 요소로 인해 가비지 수집된 힙이 손상되는 시간과 액세스 위반이 발생하는 시간 사이의 간격이 줄어듭니다.  
  
## <a name="effect-on-the-runtime"></a>런타임에 대한 영향  

 위협이 비관리 코드에서 관리 코드로 전환될 때마다 가비지 컬렉션을 발생시킵니다.  
  
## <a name="output"></a>출력  

 이 MDA는 출력을 생성하지 않습니다.  
  
## <a name="configuration"></a>구성  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [관리 디버깅 도우미를 사용하여 오류 진단](diagnosing-errors-with-managed-debugging-assistants.md)
- [gcManagedToUnmanaged](gcmanagedtounmanaged-mda.md)
- [interop 마샬링](../interop/interop-marshaling.md)
