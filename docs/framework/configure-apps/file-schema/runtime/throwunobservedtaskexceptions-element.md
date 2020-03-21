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
ms.openlocfilehash: de5a686bcbd88fc52173b488103f033575623d62
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153817"
---
# <a name="throwunobservedtaskexceptions-element"></a>\<throw관찰되지 않은태스크예외> 요소
작업 예외가 처리되지 않으면 실행 중인 프로세스를 종료할지를 지정합니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<throwun관찰태스크예외>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 처리되지 않은 작업 예외가 실행 중인 프로세스를 종료할지 여부를 지정합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|Description|  
|-----------|-----------------|  
|`false`|처리되지 않은 작업 예외에 대해 실행 중인 프로세스를 종료하지 않습니다. 이것이 기본값입니다.|  
|`true`|처리되지 않은 작업 예외에 대해 실행 중인 프로세스를 종료합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
|||  
  
## <a name="remarks"></a>설명  
 a와 <xref:System.Threading.Tasks.Task> 연관된 예외가 관찰되지 않은 경우 <xref:System.Threading.Tasks.Task.Wait%2A> 작업이 없고 부모가 연결되지 않으며 <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> 속성이 읽지 않은 작업 예외가 관찰되지 않은 것으로 간주됩니다.  
  
 .NET Framework 4에서 기본적으로 관찰되지 <xref:System.Threading.Tasks.Task> 않은 예외가 가비지 수집된 경우 종료자는 예외를 throw하고 프로세스를 종료합니다. 프로세스 종료는 가비지 수집 및 종료 시기에 따라 결정됩니다.  
  
 개발자가 작업을 기반으로 비동기 코드를 쉽게 작성할 수 있도록 .NET Framework 4.5는 관찰되지 않은 예외에 대해 이 기본 동작을 변경합니다. 관찰되지 않은 예외로 <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> 인해 이벤트가 발생하지만 기본적으로 프로세스가 종료되지 않습니다. 대신 이벤트 처리기가 예외를 준수하는지 여부에 관계없이 이벤트가 발생한 후에 예외는 무시됩니다.  
  
 .NET Framework 4.5에서는 [ \<응용](throwunobservedtaskexceptions-element.md) 프로그램 구성 파일에서 ThrowUnobservedTaskExceptions> 요소를 사용하여 예외를 throw하는 .NET Framework 4 동작을 활성화할 수 있습니다.  
  
 다음 방법 중 하나로 예외 동작을 지정할 수도 있습니다.  
  
- 환경 변수 `COMPlus_ThrowUnobservedTaskExceptions` ()를`set COMPlus_ThrowUnobservedTaskExceptions=1`설정 하 여.  
  
- 레지스트리 DWORD 값을 설정하여 ThrowUnobservedTasks = HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft에서\\1 . NETFramework 키입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 응용 프로그램 구성 파일을 사용 하 여 작업에 예외를 throw 하는 방법을 보여 주다.  
  
```xml  
<configuration>
    <runtime>
        <ThrowUnobservedTaskExceptions enabled="true"/>
    </runtime>
</configuration>  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 관찰되지 않은 예외가 작업에서 throw되는 방법을 보여 줍니다. 코드가 제대로 작동하려면 릴리스된 프로그램으로 실행되어야 합니다.  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a>참고 항목

- [런타임 설정 스키마](index.md)
- [구성 파일 스키마](../index.md)
