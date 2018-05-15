---
title: Xamarin.Essentials SMS
description: Sms 클래스에는 지정 된 보낼 메시지를 받는 사람에 게 기본 SMS 응용 프로그램을 열어 응용을 프로그램 수 있습니다.
ms.assetid: 81A757F2-6F2A-458F-B9BE-770ADEBFAB58
author: jamesmontemagno
ms.author: jamont
ms.date: 05/04/2018
ms.openlocfilehash: 5baeee03626ba659ac7e5c06be40039476a67e08
ms.sourcegitcommit: 0a72c7dea020b965378b6314f558bf5360dbd066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/09/2018
---
# <a name="xamarinessentials-sms"></a>Xamarin.Essentials SMS

![시험판 NuGet](~/media/shared/pre-release.png)

**Sms** 클래스를 사용 하면 응용 프로그램을 지정 된 보낼 메시지를 받는 사람에 게으로 기본 SMS 응용 프로그램을 엽니다.

## <a name="using-sms"></a>Sms를 사용 하 여

클래스에 Xamarin.Essentials에 대 한 참조를 추가 합니다.

```csharp
using Xamarin.Essentials;
```

호출 하 여 SMS 기능이 작동 하는 `ComposeAsync` 메서드는 `SmsMessage` 는 메시지를 받는는 모두 선택적 메시지의 본문을 포함 하 합니다.

```csharp
public class SmsTest
{
    public async Task SendSms(string messageText, string recipient)
    {
        try
        {
            var message = new SmsMessage(messageText, recipient);
            await Sms.ComposeAsync(message);
        }
        catch (FeatureNotSupportedException ex)
        {
            // Sms is not supported on this device.
        }
        catch (Exception ex)
        {
            // Other error has occurred.
        }
    }
}
```

## <a name="api"></a>API

- [Sms 소스 코드](https://github.com/xamarin/Essentials/tree/master/Essentials/Sms)
- [Sms API 설명서](xref:Xamarin.Essentials.Sms)