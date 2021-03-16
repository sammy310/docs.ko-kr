---
title: '호환성이 손상되는 변경: NotifyIcon.Text 최대 텍스트 길이가 늘어남'
description: NotifyIcon.Text 속성의 최대 텍스트 길이가 늘어난 .NET 6의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 01/19/2021
ms.openlocfilehash: f87b98dd852ce202689ae9360bee9b6cfbf01794
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255778"
---
# <a name="notifyicontext-maximum-text-length-increased"></a>NotifyIcon.Text 최대 텍스트 길이가 늘어남

<xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=nameWithType> 속성에 허용되는 최대 텍스트 길이가 63자에서 127자로 늘어났습니다.

## <a name="change-description"></a>변경 내용 설명

이전 .NET 버전에서 <xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=nameWithType> 속성에 허용되는 최대 텍스트 길이는 63자입니다. .NET 6부터 허용되는 최대 텍스트 길이가 127자입니다. 모든 버전에서 제한보다 긴 값을 설정하려고 하면 <xref:System.ArgumentException>이 throw됩니다.

## <a name="reason-for-change"></a>변경 이유

허용되는 최대 텍스트 길이가 [기본 Windows API](/windows/win32/api/shellapi/ns-shellapi-notifyicondataw#nif_showtip-0x00000080)에 맞게 늘어났습니다. Windows API는 Windows 2000에서 업데이트되었지만, 호환성 때문에 .NET Framework에서 이 속성의 크기 제한이 업데이트되지 않았습니다.

## <a name="version-introduced"></a>도입된 버전

.NET 6 미리 보기 1

## <a name="recommended-action"></a>권장 조치

코드를 검토하고 필요한 경우 기존 가드 상태를 완화합니다.

## <a name="affected-apis"></a>영향을 받는 API

<xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Windows.Forms.NotifyIcon.Text`

### Category

Windows Forms

-->
