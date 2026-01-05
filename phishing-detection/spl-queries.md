# SPL Queries Used

## Phishing Attempts Over Time

```spl
index=phishing verdict=phish
| timechart count

## Email Verdict Distribution

```spl
index=phishing
| stats count by verdict

index=phishing verdict=phish
| eval sender_domain=replace(sender,".*@","")
| stats count by sender_domain
| sort - count

index=phishing verdict=phish url!="none"
| table _time sender recipient subject url

