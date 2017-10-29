# add-points-to-map

- web form asks user to add points to a map
- pass a GET parameter to the link with the `id`: https://action-lab.github.io/add-points-to-map/?id=001
- stores results in a Google Sheet

Credits:
- by @ilyankou for @Action-Lab
- inspired by https://github.com/dwyl/html-form-send-email-via-google-script-without-server

Solution to creating appearance of a two-part form, with data recorded after each part, in case user does not complete second part:
1. Set the “target” attribute of the form to a hidden iframe in the page
2. When the user clicks “I agree to participate”, the form is submitted in that iframe
3. We get an error message (unable to display text or something) in the console because of different window origins, but nobody cares
4. The form gets replaced by the map, AND the ‘target’ attribute of the form is not the iframe but the actual document (map)
5. When user clicks “Submit”, we get the “Thank you, your answer has been recorded” message
