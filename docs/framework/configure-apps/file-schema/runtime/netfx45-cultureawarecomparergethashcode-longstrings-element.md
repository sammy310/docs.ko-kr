---
title: <NetFx45_CultureAwareComparerGetHashCode_LongStrings> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- NetFx45_CultureAwareComparerGetHashCode_LongStrings element
- <NetFx45_CultureAwareComparerGetHashCode_LongStrings> element
- GetHashCode method
- hash codes, calculating
ms.assetid: 3a5f38d1-ebc8-44de-aaeb-2929f6e6b48f
ms.openlocfilehash: 413eb6c6e61b509135601c65cf045eabd849e8b3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "74802116"
---
# <a name="netfx45_cultureawarecomparergethashcode_longstrings-element"></a>\<NetFx45_CultureAwareComparerGetHashCode_LongStrings> 요소

런타임이 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> 메서드에 대한 해시 코드를 계산하기 위해 고정된 양의 메모리를 사용할지 여부를 지정합니다.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx45_CultureAwareComparerGetHashCode_LongStrings>**  

## <a name="syntax"></a>구문

```xml
<NetFx45_CultureAwareComparerGetHashCode_LongStrings enabled="0|1">
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

|attribute|Description|
|---------------|-----------------|
|`enabled`|필수 특성입니다.<br /><br /> 해시 코드를 계산할 때 공용 언어 런타임에서 고정된 양의 메모리를 할당할지 여부를 지정합니다.|

## <a name="enabled-attribute"></a>enabled 특성

|값|Description|
|-----------|-----------------|
|0|공용 언어 런타임은 해시 코드를 계산하기 위해 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> 메서드에 가변적인 양의 메모리를 할당합니다. 기본값입니다.|
|1|공용 언어 런타임은 해시 코드를 계산하기 위해 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> 메서드에 고정적인 양의 메모리를 할당합니다.|

### <a name="child-elements"></a>자식 요소

없음

### <a name="parent-elements"></a>부모 요소

|요소|Description|
|-------------|-----------------|
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|

## <a name="remarks"></a>설명

기본적으로, 공용 언어 런타임은 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> 메서드에 가변적인 양의 메모리를 할당하고, 이 메서드가 (길이가 수백만 자 이상인) 매우 큰 문자열의 해시 코드를 컴퓨팅하려고 할 때 <xref:System.ArgumentException> 이 throw될 수 있습니다. 이 요소를 애플리케이션 구성 파일에 추가하고 `enabled` 특성을 "1"로 설정하여 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> 메서드가 해시 코드의 계산을 위해 고정된 양의 메모리를 할당하는 대체 알고리즘을 사용하도록 지정할 수 있습니다.

> [!IMPORTANT]
> `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>`요소는 Windows 8 이상 버전에서 사용 되지 않습니다.

## <a name="see-also"></a>참고 항목

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- [런타임 설정 스키마](index.md)
- [구성 파일 스키마](../index.md)
