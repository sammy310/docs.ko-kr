---
title: <ThrowUnobservedTaskExceptions> 요소
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ThrowUnobservedTaskExceptions element
- <ThrowUnobservedTaskExceptions> element
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cdce2181490d32212cd2629e98267e43bbe0d334
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674001"
---
# <a name="throwunobservedtaskexceptions-element"></a>\<ThrowUnobservedTaskExceptions > 요소
작업 예외가 처리되지 않으면 실행 중인 프로세스를 종료할지를 지정합니다.  
  
 \<configuration>  
\<runtime>  
\<ThrowUnobservedTaskExceptions>  
  
## <a name="syntax"></a>구문  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 처리 되지 않은 작업 예외에서 실행 중인 프로세스를 종료 해야 하는지 여부를 지정 합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|처리 되지 않은 작업 예외에 대해 실행 중인 프로세스를 종료 하지 않습니다. 이 값이 기본값입니다.|  
|`true`|처리 되지 않은 작업 예외에 대해 실행 중인 프로세스를 종료합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
|||  
  
## <a name="remarks"></a>설명  
 경우 연관 된 예외를 <xref:System.Threading.Tasks.Task> 지켜지지 않았습니다, 방법이 없는 <xref:System.Threading.Tasks.Task.Wait%2A> 작업을 부모 연결 되어 있지 않습니다 및 <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> 작업 예외를 관찰 하지 것으로 간주 됩니다 속성을 읽지 않았습니다.  
  
 에 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], 경우 기본값을 <xref:System.Threading.Tasks.Task> 있는 관찰 되지 않은 예외는 가비지 수집, 종료자 예외를 throw 하 고 프로세스를 종료 합니다. 프로세스의 종료는 가비지 수집 및 종료 시간에 따라 결정 됩니다.  
  
 개발자가 작업 기반 비동기 코드를 작성 하는 데 쉽게는 [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] 관찰 되지 않은 예외에 대 한이 기본 동작을 변경 합니다. 관찰 되지 않은 예외를 일으킬 수는 <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> 이벤트를 발생 하지만 기본적으로 프로세스 종료 하지 않습니다. 대신, 이벤트 처리기에서 예외를 관찰 하는 여부에 관계 없이 이벤트가 발생 한 후 예외는 무시 됩니다.  
  
 [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], 사용할 수는 [ \<ThrowUnobservedTaskExceptions > 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) 사용 하도록 설정 하려면 응용 프로그램 구성 파일에서를 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 동작의 예외를 throw 합니다.  
  
 또한 다음 방법 중 하나에서 예외 동작을 지정할 수 있습니다.  
  
- 환경 변수를 설정 하 여 `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).  
  
- DWORD 레지스트리를 설정 하 여 ThrowUnobservedTaskExceptions 값 = 1에서 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\합니다. NETFramework 키입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 응용 프로그램 구성 파일을 사용 하 여 작업의 예외 throw를 사용 하도록 설정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 작업에서 관찰 되지 않은 예외가 throw 됩니다 하는 방법을 보여 줍니다. 코드는 제대로 작동 하려면 릴리스 프로그램으로 실행 되어야 합니다.  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a>참고자료

- [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
