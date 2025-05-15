**PRIVATE TO PUBLIC**  
gh repo list Sooraj-Rao --limit 100 --json name,isPrivate --jq ".[] | select(.isPrivate == true) | .name" | for /f %i in ('more') do gh repo edit Sooraj-Rao/%i --visibility public --accept-visibility-change-consequences

**PUBLIC TO PRIVATE**
gh repo list Sooraj-Rao --limit 100 --json name,isPrivate --jq ".[] | select(.isPrivate == false) | .name" | for /f %i in ('more') do gh repo edit Sooraj-Rao/%i --visibility private --accept-visibility-change-consequences
