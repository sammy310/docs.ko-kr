---
title: .NET 라이브러리 호환성이 손상되는 변경
description: .NET Core 버전 1.0~3.0의 핵심 .NET 라이브러리 호환성이 손상되는 변경을 나열합니다.
ms.date: 07/27/2020
ms.openlocfilehash: 092ff36a5e07c9e226fe2a67d5e7cfd391e9d16b
ms.sourcegitcommit: fcbe432482464b1639decad78cc4dc8387c6269e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "97366872"
---
# <a name="core-net-libraries-breaking-changes-in-net-core-10-30"></a>.NET Core 1.0~3.0의 핵심 .NET 라이브러리 호환성이 손상되는 변경

핵심 .NET 라이브러리는 .NET Core에서 사용되는 기본 형식과 기타 일반 형식을 제공합니다.

이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.

| 주요 변경 내용 | 도입된 버전 |
| - | :-: |
| [IEnumerable\<T>를 사용하는 확장 메서드에 GroupCollection을 전달하려면 명확성 필요](#passing-groupcollection-to-extension-methods-taking-ienumerablet-requires-disambiguation) | 3.0 |
| [버전을 보고하는 API가 이제 파일 버전이 아닌 제품 버전을 보고함](#apis-that-report-version-now-report-product-and-not-file-version) | 3.0 |
| [사용자 지정 EncoderFallbackBuffer 인스턴스는 재귀적으로 대체될 수 없음](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | 3.0 |
| [부동 소수점 서식 및 구문 분석 동작 변경](#floating-point-formatting-and-parsing-behavior-changed) | 3.0 |
| [부동 소수점 구문 분석 작업은 더 이상 실패하거나 OverflowException을 throw하지 않음](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | 3.0 |
| [InvalidAsynchronousStateException이 다른 어셈블리로 이동됨](#invalidasynchronousstateexception-moved-to-another-assembly) | 3.0 |
| [잘못된 형식의 UTF-8바이트 시퀀스 교체는 유니코드 지침을 따름](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | 3.0 |
| [TypeDescriptionProviderAttribute가 다른 어셈블리로 이동됨](#typedescriptionproviderattribute-moved-to-another-assembly) | 3.0 |
| [ZipArchiveEntry가 더 이상 일치하지 않는 항목 크기의 아카이브를 처리하지 않음](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | 3.0 |
| [FieldInfo.SetValue가 초기화 전용 정적 필드에 대해 예외를 throw](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | 3.0 |
| [기본 제공 구조체 형식에 추가된 프라이빗 필드](#private-fields-added-to-built-in-struct-types) | 2.1 |
| [UseShellExecute의 기본값 변경](#change-in-default-value-of-useshellexecute) | 2.1 |
| [macOS의 OpenSSL 버전](#openssl-versions-on-macos) | 2.1 |
| [FileSystemInfo.Attributes가 throw하는 UnauthorizedAccessException](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | 1.0 |
| [손상된 프로세스 상태 예외 처리는 지원되지 않음](#handling-corrupted-state-exceptions-is-not-supported) | 1.0 |
| [UriBuilder 속성은 더 이상 앞에 선행 문자를 추가하지 않음](#uribuilder-properties-no-longer-prepend-leading-characters) | 1.0 |
| [Process.StartInfo는 코드가 시작하지 않은 프로세스에 대해 InvalidOperationException을 throw함](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | 1.0 |

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE [disambiguate-generic-type-for-groupcollection](../../../includes/core-changes/corefx/3.0/disambiguate-generic-type-for-groupcollection.md)]

***

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/3.0/version-information-changes.md)]

**_

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/3.0/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

_*_

[!INCLUDE[Floating point formatting and parsing behavior changes](~/includes/core-changes/corefx/3.0/floating-point-changes.md)]

_*_

[!INCLUDE[Floating-point parsing operations no longer fail or throw an OverflowException](~/includes/core-changes/corefx/3.0/floating-point-parsing-does-not-overflow.md)]

_*_

[!INCLUDE[InvalidAsynchronousStateException moved to another assembly](~/includes/core-changes/corefx/3.0/move-invalidasynchronousstateexception.md)]

_*_

[!INCLUDE[NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences](~/includes/core-changes/corefx/3.0/net-core-3-0-follows-unicode-utf8-best-practices.md)]

_*_

[!INCLUDE[TypeDescriptionProviderAttribute moved to another assembly](~/includes/core-changes/corefx/3.0/move-typedescriptionproviderattribute.md)]

_*_

[!INCLUDE[ZipArchiveEntry no longer handles archives with inconsistent entry sizes](~/includes/core-changes/corefx/3.0/ziparchiveentry-and-inconsistent-entry-sizes.md)]

_*_

[!INCLUDE [FieldInfo.SetValue throws exception for static, init-only fields](~/includes/core-changes/corefx/3.0/fieldinfo-setvalue-exception.md)]

_*_

## <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

_*_

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

_*_

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

_*_

## <a name="net-core-10"></a>.NET Core 1.0

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

_*_

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

_*_

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

_*_

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

_**
