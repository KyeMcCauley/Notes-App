# Notes-App

THE LIQUID GLASS MANUAL
Think of this as your survival guide for the code we just built. Since you’re coding on the move using Koder, things can get a little messy when copy-pasting. This guide breaks down how to keep your app alive and thriving.
 * APP ARCHITECTURE: WHAT'S UNDER THE HOOD?
Your app is a Single Page Application (SPA). Instead of different files, it uses one file and "hides" the parts you aren't looking at.
 * STYLES (CSS): Located in the <style> block. Handles the "Liquid Glass" look: blurs, transparency, and the 3-column drawing layout.
 * STRUCTURE (HTML): Located in the <body> block. The "bones." It defines the Home, Note, Draw, and Camera containers.
 * THE BRAIN (JS): Located in the <script> block. Handles the logic: switching tabs, drawing on the canvas, and processing colors.
 * THE VIEWPORTS: Controlled by the .view-page class. These are the specific screens. The switchTab() function toggles the .active class to show/hide them.
<!-- end list -->
 * THE "I BROKE IT" SURVIVAL GUIDE
Mobile editors like Koder are great, but one accidental thumb-swipe can delete a crucial character. If the app stops working, check these three spots:
THE "DANGLING DIV" CHECK
If your layout looks like it went through a blender, you likely deleted a </div> tag.
 * THE FIX: Ensure every section (like #draw-view) has its own closing </div> before the next section starts.
 * THE GOLDEN RULE: There should be TWO </div> tags right before the comment. One closes the current view, the other closes the entire app container.
THE SCRIPT "BLACKOUT"
If the app looks perfect but buttons do nothing, the JavaScript is dead.
 * THE FIX: Scroll to the bottom. Make sure your code ends exactly with:
   </script>
   </body>
   </html>
 * If you see code after the </script> tag, move it inside or delete it.
<!-- end list -->
 * HOW TO UPGRADE YOUR APP
Ready to take this from a prototype to a pro tool? Here are your next move options:
 * PERSISTENT MEMORY: Currently, notes vanish if you refresh. Upgrade by using localStorage.setItem() inside the saveNote() function.
 * TRUE LAYERS: Right now, the Layers panel is just a visual placeholder. You can upgrade this by creating an array of canvases stacked on top of each other.
 * ADVANCED "DROP-TO-FILL": The current fill is a placeholder. To make it real, you’ll need a Flood Fill Algorithm (check out the "Recursive Stack" method for JS).
<!-- end list -->
 * LIKELY BUG FIXES
PROBLEM: Canvas is blank
 * CAUSE: Canvas initialized before the page loaded.
 * SOLUTION: Ensure resizeCanvas() is called inside the window.onload event.
PROBLEM: Drawing is offset
 * CAUSE: The touch coordinates aren't accounting for the sidebar.
 * SOLUTION: Check getPos(e). It must subtract rect.left and rect.top from the touch point.
PROBLEM: Icons are missing
 * CAUSE: Emojis vary by iOS version.
 * SOLUTION: Replace the emoji (e.g., the pen symbol) with an SVG icon or plain text.
PROBLEM: Camera won't open
 * CAUSE: Missing capture="environment" attribute.
 * SOLUTION: Ensure the hidden <input type="file"> has the capture attribute for native camera access.
PRO DEBUGGING TIP: If you're stuck, add console.log("I am here"); inside a function. In Koder's preview, look for a "Console" or "Log" button to see if your code is actually reaching that point!